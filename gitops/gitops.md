# GitOps - Frequently Asked Questions

## How does GitOps differ from Infrastructure as Code?
Infrastructure as code is a pattern, rather than a specific workflow.  Today Infrastructure as Code (IaC), no matter how it was originally intended, has a lot of different meanings that have been implemented in a variety of ways.  

## GitOps is a prescriptive style of Infrastructure as Code for the cloud native era and it builds on and combines:

Orchestration
Observability
Declarative Infrastructure as Code
Containers and Immutable Infrastructure
DevOps best practices
One of the main differences between IaC and GitOps is the use of immutable containers as deployable artefacts that can be converged on by a suitable orchestration tool, for example Kubernetes. Your desired state is kept in source control. This isn’t always the case with some of the infrastructure as code tools. IaC implementations vary, and sometimes the source of truth is split between a git repo, and a database, and sometimes spread between a weakly-linked union of multiple git repos.

For example, some configurations of Puppet do provide the same overall workflow as GitOps does, where changes are pushed and are converged on automatically. Some even use Puppet Master to alert when the infrastructure varies from what is defined, but that wasn’t widely done back when these tools were first implemented.

While Infrastructure as Code tools provide a way to manage infrastructure, they don’t manage the entire Cloud Native stack. GitOps on the other hand, allows you to manage the whole platform.

With GitOps you can use Infrastructure as Code tools to perform any infrastructure updates through Git.  In our experience, Terraform works well with GitOps, but still requires some human oversight.  So in this sense, GitOps extends the tradition of Infrastructure as Code tools.

Others have said that GitOps is an extension of infrastructure as Code like this article in the ACM journal: GitOps: A Path to More Self-service IT.

“GitOps is to Infrastructure as Code as Microservices are to SOA or XP is to Agile.” -- Alexis Richardson, CEO of Weaveworks

## What is the “convergence mechanism”?
When configuration updates are made through Git, the Kubernetes orchestrator keeps applying changes to the cluster until its state has converged with the updated configuration in Git.  This model works for any Kubernetes resource and is also extensible using Kubernetes Custom Resource Definitions (CRDs).

## When an update occurs, the following happens:

The cluster is observed and compared with Git.  
On convergence a notification for deployment success is sent.  
On divergence an alert is sent and if set a convergence is triggered.  
The mechanisms for this convergence can be communicated via Diff alerts in Terraform or via Weave Cloud’s deployment automator.

## Can I use a CI server to orchestrate convergence in the cluster?
Your CI server is not an orchestration tool.  You need something that continually attempts to make progress (until there are no more diffs). CI fails when it encounters a difference.  In combination with a human operator, a CI server can be made to force convergence, but this creates other issues. For example your CI scripts might not be able to enforce an idempotent and/or atomic group of changes.  

Also if something breaks (and it will) then you could end up being in a partial and unknown state that requires a full reboot to fix.  It is easier to use dedicated orchestrators like Kubernetes and Terraform to provide convergence rather than relying on your CI tool to do that.

## Should I abandon my CI tool?
No!  Please keep on using your CI server to orchestrate the development of merging to mainline, building and testing.

But you shouldn’t use CI servers to do continuous delivery.

A GitOps pipeline is an improvement on existing CICD pipelines where the CI engine (like Jenkins) is responsible for orchestrating updates but then may not complete correctly and simply fail.

CI is used to merge and integrate updates with the trunk, and with GitOps we rely on Kubernetes or the cluster to internally manage deployments based on those trunk updates.

We also call this the “pull” model for CD.

## Why is a PULL vs a PUSH pipeline important?
Most CICD tools available today use a push-based model. A push-based pipeline means that code starts with the CI system and then continues its path through a series of encoded scripts to push changes to the Kubernetes cluster.

The reason you don’t want to use your CI system as the basis for your deployments is because of the potential to expose credentials outside of your cluster. While it is possible to secure your CI scripts, you are still working outside the trust domain of your cluster which is not recommended.

In a pull pipeline, a Kubernetes Operator deploys new images from inside of the cluster (in our case, Weave Cloud provides one for you). The operator notices when a new image has been pushed to the registry. Convergence of the cluster state is then triggered and the new image is pulled from the registry, the manifest is automatically updated and the new image is deployed to the cluster.  

With a pipeline that pulls an image from the repository, your cluster credentials are not exposed outside of your production environment.

## What is an Observed State?
We cannot say what actual state is.  We can only observe it. This is why diffs are so important.

Observability is an integral part of GitOps, where we alert on a divergence and then converge the ‘actual’ system if it differs from ‘the source of truth’.

## How do you know whether or not a cluster update succeeded?
When you want to know whether a transactional update in Git has led to a correct update in the cluster:

The cluster needs to be observed and compared with what’s in Git.  
If deployments are forthcoming - or a convergence--  you should be notified for success.
On a divergence there should be an alert that triggers a convergence.  
See GitOps Part 3 - Observability for more information.

## Why is the Developer Experience important?
GitOps is part of a new generation of workflows and tools that share the goal of making Kubernetes easy to use.  

Git workflows can now be applied to both operations, and development.   Every developer on your team is likely familiar with Git and can make pull requests. Now they can use Git to accelerate and simplify application deployments to Kubernetes as well.

## What if I don’t want to use Git?
While many developers like using Pull Requests to drive operational changes, not all of them like the Git user experience.  Also, in some cases (not many), writing to Git can add latency.

It is perfectly reasonable to imagine advanced GUIs with a pleasant UI/UX that write commits to Git.  These might be used in, for example, traffic management. We can also imagine pre-commits to the cluster that write behind (or through) to Git.

## Is GitOps Atomic Deployment?
It would be really cool if we could have “atomic deployments” in which all updates are applied, or none. Git is a transactional system, so can we use GitOps to provide transactional behaviours to Kubernetes deployments?  Alas, this is not in general possible. In Kubernetes, updates are NOT always transactions.

Here is what we can say:

Kubernetes is capable of trying to apply a set of updates as a single group.  This is because it is convergent and idempotent.
However Kubernetes cannot guarantee success of a group of updates.  For example in a group of three updates, one may fail.  This is a so-called “partial failure”.
Kubernetes can report what failed, and the orchestrator can proceed from a partial failure towards success.  Efficiency matters - we don't want to have to boot 100 machines 1000 times a day.
There is a known rollback state, ie. the desired state of the previous Git transaction in the log.  
As far as we can tell this is about as close as we can usefully get towards the dream of transactional operations.  It’s better than by-hand approaches and scripts.


## Why choose Git and not a Configuration Database instead?
Choosing Git to store the declarative specification is almost arbitrary, since any modern revision control system would work here.  However:

We can easily maintain a versioned set of desired states in Git, that form a linear order in trunk for the history of an environment, and a partial order for variant environments.
Configuration can be in human & machine readable text.
Code is stored in image repos – containers are an aspect of immutable infrastructure.
Git has desirable immutability and non-repudiation properties.  In particular we have an irrevocable and indisputable log for transactions, rollback, audit; it is also a social log so that developers can provide explanatory contextual comments.
When you use a Git repo manager like GitHub, you also get native support for peer review. Also single or even multiple approval lifecycles can lower the risk of changes and satisfy any segregation of duty obligations. 
All this is better than using a DB.


## What is meant by the “whole system”?
In GitOps an environment consists of more than just Kubernetes.  We should use the same principles to manage the whole environment, ie.:

Declarative infrastructure if not on bare metal.
Indeed, declarative everything else: app config; machine config; policy rules; routing rules; dashboards, alerts, etc.
Via Git, configuration management of hosts with declarative state.
How do you manage secrets?
You don’t want to keep any secrets in Git where they are left open to anyone who has access to your repo.  If you are embracing GitOps in your organization, cluster secrets should be managed with something like HashiCorp’s Vault, or you can use Sealed Secrets from Bitnami.  

Sealed-secrets solves the following problem: "I can manage all of my Kubernetes configs in Git, except Secrets."  Sealed Secrets is a Kubernetes Custom Resource Definition Controller that lets you to store sensitive information (aka secrets) in Git.

See Secure GitOps Using Weave Cloud Deploy And Bitnami's Sealed Secrets for a step by step guide on to how use sealed secrets with Weave Cloud.

## How does GitOps work with databases or other stateful applications?
Databases or any service with persistent data will need to be handled differently.  You can use GitOps to manage changes, but you’ll need to ensure that your database schemas can be updated along with the rest of your code.  To learn more about how to handle databases during a rolling update, see the post, “How to Correctly Handle DB Schemas During Kubernetes Rollouts.”