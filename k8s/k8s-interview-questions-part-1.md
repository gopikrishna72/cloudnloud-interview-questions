Topic is Divided into following sections, I know these are overlapping sections it's difficult to distinguish between them:

- Administration
- Compute 
- Storage
- Network 
- Security
- Monitoring
- Logging 


#### Administration

**Q: What is orchestration in software and DevOps?**

A: In software development, orchestration refers to the integration of multiple applications or services, allowing them to automate a process or synchronize their data in real-time. If an application runs on multiple microservices that are placed in separate containers, orchestration helps the services communicate seamlessly to achieve a goal.

Q: How does Kubernetes help with orchestration?

A: Kubernetes is an open-source orchestration tool that helps in simplifying DevOps tasks like deployment, scaling, configuration, and others. Most distributed applications are hosted and run in containers. A container is an isolated environment in which the microservices of the app can run together. These containers are managed externally, and they must be scheduled, distributed, and load-balanced to support the infrastructure. But managing these containers becomes challenging in a clustered environment due to data persistence and network configurations.

Kubernetes (blog to get started with Kubernetes) can help overcome these challenges and easily manage a cluster of containers. It can link and orchestrate several containers running on multiple hosts. Kubernetes can manage applications that run on a cluster of hundreds of individual servers. It eliminates most of the manual processes in deploying and scaling containerized applications. Kubernetes allows you to fully implement and fully harness a container-based infrastructure.

Q: What is a node in Kubernetes?

A: A node is the smallest fundamental unit of computing hardware. It represents a single machine in a cluster, which could be a physical machine in a data center or a virtual machine from a cloud provider. Each machine can substitute any other machine in a Kubernetes cluster. The master in Kubernetes controls the nodes that have containers. 

Q: What is Kubernetes?

A: Kubernetes is an open-source container orchestration tool or system that is used to automate tasks such as the management, monitoring, scaling, and deployment of containerized applications. It is used to easily manage several containers (since it can handle grouping of containers), which provides for logical units that can be discovered and managed. This is an important Kubernetes Interview Questions

Q: How are Kubernetes and Docker related?

A: Docker is an open-source platform used to handle software development. Its main benefit is that it packages the settings and dependencies that the software/application needs to run into a container, which allows for portability and several other advantages. Kubernetes allows for the manual linking and orchestration of several containers, running on multiple hosts that have been created using Docker. 

Q: What are the main differences between the Docker Swarm and Kubernetes?

A: 

- Docker Swarm is Docker’s native, open-source container orchestration platform that is used to cluster and schedule Docker containers. Swarm differs from Kubernetes in the following ways:

- Docker Swarm is more convenient to set up but doesn’t have a robust cluster, while Kubernetes is more complicated to set up but the benefit of having the assurance of a robust cluster
- Docker Swarm can’t do auto-scaling (as can Kubernetes); however, Docker scaling is five times faster than Kubernetes 
- Docker Swarm doesn’t have a GUI; Kubernetes has a GUI in the form of a dashboard 
- Docker Swarm does automatic load balancing of traffic between containers in a cluster, while Kubernetes requires manual intervention for load balancing such traffic  
- Docker requires third-party tools like ELK stack for logging and monitoring, while Kubernetes has integrated tools for the same 
- Docker Swarm can share storage volumes with any container easily, while Kubernetes can only share storage volumes with containers in the same pod
- Docker can deploy rolling updates but can’t deploy automatic rollbacks; Kubernetes can deploy rolling updates as well as automatic rollbacks


Q: What is the role of clusters in Kubernetes?

A: Kubernetes allows you to enforce the required state management by feeding cluster services of a specific configuration. Then, these cluster services run that configuration in the infrastructure. The following steps are involved in the process:

The deployment file contains all the configurations to be fed into the cluster services.
The deployment file is fed into the API.
Now, the cluster services schedule the pods in the environment
Cluster services also ensure that the right number of pods are running
So, the Kubernetes cluster is essentially made up of the API, the worker nodes, and the Kubelet process of the nodes.

Q: What is Kubectl used for?

A: Kubectl is a tool for controlling Kubernetes clusters. In fact, “ctl” stands for control. It is a command-line interface that allows you to pass commands to the cluster and manage the Kubernetes component. This is an important Kubernetes Interview Questions

Q: How can you run Kubernetes locally?

A: You can run Kubernetes locally using the Minikube tool. It runs a single-node cluster inside a virtual machine on your laptop. So, it provides an efficient way for users who are just getting started and want to try out Kubernetes.

Q: What is Heapster?

A: Heapster is a performance monitoring and metrics collection tool supported natively on the Kubernetes cluster. It runs like any other pod in the cluster, discovering all nodes and querying information from Kubernetes nodes. This container management tool works via an on-machine agent. 

Q: What are the different components of Kubernetes Architecture?

A: The Kubernetes Architecture has mainly 2 components – the master node and the worker node. As you can see in the below diagram, the master and the worker nodes have many inbuilt components within them. The master node has Kube-controller-manager, Kube-apiserver, kube-scheduler, etc. Whereas the worker node has kubelet and Kube-proxy running on each node.

Q: What are federated clusters?

A: Multiple Kubernetes clusters can be managed as a single cluster with the help of federated clusters. So, you can create multiple Kubernetes clusters within a data center/cloud and use the federation to control/manage them all in one place.

The federated clusters can achieve this by doing the following two things. Refer to the below diagram.

Q: What is a Headless Service?

A: Headless Service is similar to that of a ‘Normal’ services but does not have a Cluster IP. This service enables you to directly reach the pods without the need of accessing it through a proxy.

Q: What do you understand by load balancer in Kubernetes?

A: A load balancer is one of the most common and standard ways of exposing service. There are two types of load balancers used based on the working environment i.e. either the Internal Load Balancer or the External Load Balancer. The Internal Load Balancer automatically balances load and allocates the pods with the required configuration whereas the External Load Balancer directs the traffic from the external load to the backend pods.

Q: Name the initial namespaces from which Kubernetes starts?

Default
Kube – system
Kube – public

Q: What is the Kubernetes controller manager?

A: The controller manager is a daemon that is used for embedding core control loops, garbage collection, and Namespace creation. It enables the running of multiple processes on the master node even though they are compiled to run as a single process.

Kubernetes Interview Questions 

Q: What is a pod in Kubernetes?

A: Pods are high-level structures that wrap one or more containers. This is because containers are not run directly in Kubernetes. Containers in the same pod share a local network and the same resources, allowing them to easily communicate with other containers in the same pod as if they were on the same machine while at the same time maintaining a degree of isolation.

Q: What is the job of the kube-scheduler?

A: The kube-scheduler assigns nodes to newly created pods.

Q: What is orchestration when it comes to software and DevOps? 

A: Orchestration refers to the integration of multiple services that allows them to automate processes or synchronize information in a timely fashion. Say, for example, you have six or seven microservices for an application to run. If you place them in separate containers, this would inevitably create obstacles for communication. Orchestration would help in such a situation by enabling all services in individual containers to work seamlessly to accomplish a single goal. 

Q: What is ETCD in Kubernetes?

A: Etcd is a store for the configuration, state, and metadata of Kubernetes clusters. It is written in Go programming language and represents the cluster state at a given point in time. This datastore serves as the backbone of distributed systems. 

Q: What do you understand by container resource monitoring?

A: From the user perspective, it is vital to understand resource utilization at different abstraction layers and levels, like container pods, services, and the entire cluster. Each level can be monitored using various tools, namely:

Grafana
Heapster
InfluxDB
CAdvisor
Prometheus

Q: What benefits does Kubernetes offer?

A: Kubernetes makes the handling of containers very easy. It helps you deploy applications faster, leading to an improved response to customer demands. Kubernetes helps automate scheduling and rollbacks. Kubernetes is also ideal for cloud-native apps requiring rapid scaling since it can cluster together groups of hosts across private, public, or hybrid clouds.

Q: What are namespaces in Kubernetes?

A: A namespace in Kubernetes is used to divide the resources in the cluster among multiple users. This is particularly helpful in environments where there are multiple users scattered over a vast area geographically.

Q: What is a node in Kubernetes?

A: A node is the smallest unit in the computing system. It is a single machine in a cluster formerly referred to as a minion since it is a worker unit that runs the pods. It can be either a physical machine or a virtual machine and is controlled by the master components in the Kubernetes system.

Q: What are the two main components of the Kubernetes architecture?

A:  The Kubernetes architecture has two primary components – the master node and worker nodes. The master node consists of the API server, the scheduler, the controller manager, and the etcd components. The worker nodes have services such as container run time and Kube proxy that run on each node.

Q: What is the role of a pod?

A: A pod in Kubernetes is responsible for holding individual containers. Each pod can hold various containers depending on the configurations and requirements. The containers held within a single pod share the same resources and the same local network, which makes it easier for them to communicate.

Q: Where is the cluster data stored in Kubernetes?

A: The main data storage component in the Kubernetes system is the etcd. This is where the cluster data is stored.

Q: What is the difference between a pod and a job in Kubernetes?

A: The difference lies in their individual functions. The function of a pod is to ensure that a container is running. The function of a job is to ensure that the pods run to the completion of the job.

Q: What is a kubelet?

A: A kubelet can be considered the lowest level component in the Kubernetes system. Its function is to control a set of pods and ensure that all the containers in a given pod are running throughout its lifecycle.

Q: What is kube-proxy?

A: Kube-proxy manages the host sub-netting and makes services available to other components of the system. Its function is to direct to correct containers based on the IP and port number of incoming requests, thus helping with load balancing.

Q: What is a Heapster in Kubernetes?

A: Heapster is a performance monitoring tool in Kubernetes. It works like just another pod in the cluster and collects metrics on all nodes. It has native support on Kubernetes.

Q: What is a scheduler in the Kubernetes architecture?

A: A scheduler, or kube-scheduler, is responsible for distributing the workload among the worker nodes. It schedules the tasks and monitors the resource use for each node to ensure the distribution is done correctly.

Q: What are Daemon sets?

A: Daemon sets are a set of pods that are made to run on a host, only once. They are used for host layer attributes, like network monitoring, which are usually run only once on a host.

Q: How do you determine that a pod is always running?

A: This can be determined by introducing probes, such as a liveness probe. It can check if the application inside a pod is running. If it shows failure, the container will get restarted.

Q: What are a few different ways to provide API security on Kubernetes?

A: To provide API security on Kubernetes, some methods we can use are:

Use the correct authorization mode with the API server
Use API authentication
Ensure that all incoming traffic is protected by TLS
Use authorization-mode=Webhook to make kubeless protect the API
Use restrictive RBAC role policy on the kube-dashboard
Remove any default service account permissions


Q: What is load balancing in Kubernetes?

A: The load balancing process allows you to expose services to the internet. Internal load balancing refers to automatically balancing the loads on pods and allocating them with the required configuration. External load balancing refers to directing traffic from external loads to the backend pods.

Q: What is a controller manager, and what are its types?

A: The Kubernetes controller manager is a daemon used for embedding core control loops that regulate the system. It helps to run multiple processes on the Master node.

Q: What are the uses of the Google Kubernetes Engine?

A: The GKE, also known as Google Container Engine, is a management platform for Docker containers and clusters. GKE lets you orchestrate container clusters that run within Google’s public cloud services.

Q: How is Kubernetes different from Docker Swarm?

A: Docker Swarm is a default orchestration tool that comes integrated with Docker. It can orchestrate simple Docker containers. Docker Swarm does not do auto-scaling or deploy automatic rollbacks.
Kubernetes is also an orchestration tool, but it can manage much more complex applications as it has a more robust cluster. Kubernetes performs auto-scaling and automatic rollbacks.
Docker Swarm is easier to install, though, as compared to Kubernetes. Docker Swarm also does automatic load balancing between containers, which is not possible in Kubernetes. So, both tools have their set of pros and cons.

Q: How to do maintenance activity on K8 node?

A: Maintenance activity are inevitable part of administration, you may need to do the patching or apply some security fixes on K8. Mark the node unschedulable and then drain the PODs which are present on K8 node.

 - kubectl cordon <hostname>
 - kubectl drain --ignore-daemonsets <hostname>

It's important to include the `--ignore-daemonsets` for any daemonset running on this node. Just in case if any statefulset is running on this node, and if no more node is available to maintain the count of statesful set then statesfulset POD will be in pending status. 

Q: What is role of a pause container?

A: Pause container servers as the parent container for all the containers in your POD. 

- It serves as the basis of Linux namespace sharing in the POD. 
- PID 1 for each POD to reap the zombie processes. 

https://www.ianlewis.org/en/almighty-pause-container

Q: Why we need service mesh?

A: A service mesh ensures that communication among containerized and often ephemeral application infrastructure services is fast, reliable, and secure. The mesh provides critical capabilities including service discovery, load balancing, encryption, observability, traceability, authentication and authorization, and support for the circuit breaker pattern.

Q: How to control the resource usage of a POD?

A: With requests and limits resource usage of a POD can be control. 

request: the amount of resources being requested for a container. If a container exceeds its request for resources, it may be throttled back down to it’s request.

limit: an upper cap on the resources a container is able to use. If it tries to exceed this limit it may be terminated if Kubernetes decides that another container needs the resources. If you’re sensitive to pod restarts, it makes sense to have the sum of all container resource limits equal or less than the total resource capacity for your cluster.

https://www.noqcks.io/notes/2018/02/03/understanding-kubernetes-resources/

Q: What are the units of CPU and memory in POD definition?

A: CPU is in milicores and memory in bytes. CPU can be easily throttled but not memory. 

Q: Where else we can set a resource limit?

A: You may also set resource limit on a namespace. This is helpful in scenarios where people have habit of not defining the resource limits in POD definition. 

Q: How will you update the version of K8?

A: Before doing the update of K8, it's important to read the release notes to understand the changes introduced in newer version and whether version update will also update the etcd. 

https://kubernetes.io/docs/tasks/administer-cluster/kubeadm/kubeadm-upgrade-1-12/

Q: Difference between helm and K8 operator?

A: An Operator is an application-specific controller that extends the Kubernetes API to create, configure and manage instances of complex stateful applications on behalf of a Kubernetes user. It builds upon the basic Kubernetes resource and controller concepts, but also includes domain or application-specific knowledge to automate common tasks better managed by computers. On the other hand, helm is a package manager like yum or apt-get. 

Q: Explain the role of CRD (Custom Resource Definition) in K8?

A: A custom resource is an extension of the Kubernetes API that is not necessarily available in a default Kubernetes installation. It represents a customization of a particular Kubernetes installation. However, many core Kubernetes functions are now built using custom resources, making Kubernetes more modular.

Q: What are the various K8 related services running on nodes and role of each service?

A: Mainly K8 cluster consists of two type of nodes: master and executor

- master services:

  - kube-apiserver: Master API service which acts like a door to K8 cluster. 
  - kube-scheduler: Schedule PODs according to available resources on executor nodes. 
  - kube-controller-manager: controller is a control loop that watches the shared state of the cluster through the 
    apiserver and makes changes attempting to move the current state towards the desired state

- executor node: (These also runs on master node)

  - kube-proxy: The Kubernetes network proxy runs on each node. This reflects services as defined in the Kubernetes API on 
    each node and can do simple TCP, UDP, and SCTP stream forwarding or round robin TCP, UDP, and SCTP forwarding across a set of backends.
  - kubelet: kubelet takes a set of PodSpecs that are provided through various mechanisms (primarily through the 
    apiserver) and ensures that the containers described in those PodSpecs are running and healthy

Q: Recommended way of managing the access to multiple clusters?

A: kubectl looks for the config file, multiple clusters access information can be specified in this config file. `kubectl config` commands can be used to manage the access to these clusters. 

Q: What is PDB (Pod Disruption Budget)?

A: A PDB specifies the number of replicas that an application can tolerate having, relative to how many it is intended to have. For example, a Deployment which has a .spec.replicas: 5 is supposed to have 5 pods at any given time. If its PDB allows for there to be 4 at a time, then the Eviction API will allow voluntary disruption of one, but not two pods, at a time. This is applicable for voluntary disruptions.

Q: In what situations daemonsets are normally used?

A: Daemonset are used to start the PODs on every node in cluster. It's used generally to run the monitoring or logging agents which are supposed to run on every executor node in cluster. 

Q: When stateful sets are preferred?

A: When you are running the applications which require quorum basically the applications which are not truely stateless for those applications stateful sets are required. 

Q: What's init container and when it can be used?

A: init containers will set a stage for you before running the actual POD. 

- Wait for some time before starting the app Container with a command like sleep 60.
- Clone a git repository into a volume.

Q: What are the application deployment strategies?

A: In this agile world there is continuous demand of upgrading the applciations, we have multiple options for deploying the new version of app:

1) Recreate: Old style, existing application version is destroyed and new version is deployed. Significant amount of downtime. 
2) Rolling update: Gradually bringing down the existing deployment and introducing the new versions. You decide how many instances can be upgraded at single point of time. 
3) Shadow: Traffic going to existing version of application is replicated to new version to see it's working. Istio provide this pattern. 
4) A/B Testing using Istio: Running multiple variants of application together and determines the best one based on user traffic. It's more for managment decisions.
5) Blue/Green : Blue is mainly about switching the traffic from one version of app to another version. 
6) Canary deployment : In which certain percentage of traffic is shifted from one version to another. If things work well we will keep on increasing the traffic shift. It's different from the rolling update in which existing version count is reduced gradually. 

#### Compute

Q: How to troubleshoot if the POD is not getting scheduled? 

A: There are many factors which can led to unstartable POD. Most common one is running out of resources, use the commands like `kubectl desribe <POD> -n <Namespace>` to see the reason why POD is not started. Also, keep an eye on `kubectl get events` to see all events coming from the cluster. 

Q: How to run a POD on particular node?

A: Various methods are available to achieve it. 

- nodeName: specify the node name in POD spec, it will try to run the POD on specific node. 

- nodeSelector : you may assign a specific lable to node which have special resources and use the same label in POD spec so that POD will run only on that node. 

- nodeaffinities: requiredDuringSchedulingIgnoredDuringExecution, preferredDuringSchedulingIgnoredDuringExecution are hard, soft requirements for running the POD on specific nodes. This will be replacing nodeSelector in future. It depends on the node labels. 

Q: How to ensure PODs are colocated to get performance benefits?

A: podAntiAffinity and podAffinity are the affinity concept to not keep and keep the PODs on same node. Key point to note is that it depends on the POD labels. 

Q: What are the taints and toleration?

A: Taints allow a node to repel a set of pods. You can set taints on the node and only the POD which have tolerations matching the taints condition will be able to run on those nodes. This is useful in the case when you allocated node for one user and don't want to run the PODs from other users on that node. 

#### Storage

Q: How to provide persistent storage for POD?

A: Persistent volumes are used for persistent POD storage. They can be provision statically or dynamically. 

Static : A cluster administrator creates a number of PVs. They carry the details of the real storage which is available for use by cluster users. 

Dynamically : Administrator creates a PVC (Persistent volume claim) specifying the existing storage class and volume created dynamically based on PVC.

#### Network

Q: How two containers running in a single POD have single IP address?

A: Kubernetes implements this by creating a special container for each pod whose only purpose is to provide a network interface for the other containers. These is one `pause` container which is responsible for namespace sharing in the POD. Generally, people ignore the existance of this pause container but actually this container is the heart of network and other functionalities of POD. It provides a single virtual interface which is used by all containers running in a POD.  

Q: What are the various ways to provide external world connectivity to K8?

A: By default POD should be able to reach the external world but for vice-versa we need to do some work. Following options are available to connect with POD from outer world. 

- Nodeport (it will expose one port on each node to communicate with it)
- Load balancers (L4 layer of TCP/IP protocol)
- Ingress (L7 layer of TCP/IP Protocol)

One another method is kube-proxy which can be used to expose a service with only cluster IP on local system port. 

$ kubectl proxy --port=8080
$ http://localhost:8080/api/v1/proxy/namespaces/<NAMESPACE>/services/<SERVICE-NAME>:<PORT-NAME>/

https://medium.com/google-cloud/kubernetes-nodeport-vs-loadbalancer-vs-ingress-when-should-i-use-what-922f010849e0

Q: What's the difference between nodeport and load balancer?

A: nodport relies on the IP address of your node. Also, you can use the node ports only from the range 30000–32767, on another hand load balancer will have it's own IP address. All the major cloud providers supports creating the LB for you if you specify LB type while creating the service. On baremetal based clusters, metallb is promising.  

Q: When we need ingress instead of a LB? 

A: For each service you have one LB. You can have single ingress for multiple services. This will allow you do both path based and subdomain based routing to backend services. You can do the SSL termination at ingress. 

Q: How POD to POD communication works?

A: For POD to POD communication, it's always recommended to use the K8 service DNS instead of POD IP because PODs are ephemeral and their IPs can get change after the redeployment. 

If the two PODs are running on a same host then physical interface will not come into the picture. 

- Packet will leave POD1 virtual network interface and go to docker bridge (cbr0).
- Docker bridge will forward the packet to right POD2 which is running on same host.  

If two PODs are running on a different host then physical interface of both host machines will come into the picture. Let's consider a scenario in which CNI is not used. 

POD1 = 192.168.2.10/24 (node1, cbr0 192.168.2.1)
POD2 = 192.168.3.10/24 (node2, cbr1 192.168.3.1)

- POD1 will send the traffic destined for POD2 to it's GW (cbr0) because both are in different subnet. 
- GW doesn't know about 192.168.3.0/24 network hence it will forward the traffic to physical interface of node1. 
- node1 will forward the traffic to it's own physical rourter/gateway.
- That physical router/GW should have the route for 192.168.3.0/24 network to route the traffic to node2.
- Once traffic reaches node2, it pass that traffic to POD2 through cbr1

If the Calico CNI it's responsible for adding the routes for cbr (docker bridge IP address) in all nodes. 

Q: How POD to service communication works?

A: PODs are ephemeral their IP address can change hence to communicate with POD in reliable way service is used as a proxy or load balancer. A service is a type of kubernetes resource that causes a proxy to be configured to forward requests to a set of pods. The set of pods that will receive traffic is determined by the selector, which matches labels assigned to the pods when they were created. K8 provides an internal cluster DNS that resolves the service name. 

Service is using different internal network than POD network. netfilter rules which are injected by kube-proxy are used to redirect the request actually destined for service IP to right POD. 

Q: How does service knows about healthy endpoints?

A: kubelet running on worker node is responsible for detecting the unhealth endpoints, it passes that information to API server then eventually this information is passed to kube-proxy which wil adjust the netfilter rules accordingly. 

I highly recommend reading the following series to get solid understanding about the K8 networking. 

https://medium.com/google-cloud/understanding-kubernetes-networking-pods-7117dd28727

https://medium.com/google-cloud/understanding-kubernetes-networking-services-f0cb48e4cc82

https://medium.com/google-cloud/understanding-kubernetes-networking-ingress-1bc341c84078


#### Security

Q: What are the various things can be done to increase the K8 security?

A: This is a huge topic, I am sharing some thoughts on it.

- By default, POD can communicate with any other POD, we can setup network policies to limit this communication between the PODs.
- RBAC (Role based access control) to narrow down the permissions. 
- Use namespaces to establish security boundaries. 
- Set the admission control policies to avoid running the priviledged containers. 
- Turn on audit logging.

#### Monitoring

Q: How to monitor K8 cluster? 

A: Prometheus is used for K8 monitoring. Prometheus ecosystem consists of multiple components. 

- main Prometheus server which scrapes and stores time series data
- client libraries for instrumenting application code
- a push gateway for supporting short-lived jobs
- special-purpose exporters for services like HAProxy, StatsD, Graphite, etc.
- an alertmanager to handle alerts
- various support tools

Q: How to make prometheus HA?

A: You may run multiple instances of prometheus HA but grafana can use only of them as a datasource. You may put load balancer in front of multiple prometheus instances, use sticky sessions and failover if one of the prometheus instance dies. This make things complicated. Thanos is another project which solve these challenges. 

Q: What are other challenges with prometheus?

A: Desipte of being very good at K8 monitoring, prometheus still have some issues: 

- Prometheus HA support.
- No downsampling is available for collected metrics over the period of time. 
- No support for object storage for long term metric retention.

All of these challenges are again overcome by Thanos.   

Q: What's prometheus operator?

A: The mission of the Prometheus Operator is to make running Prometheus on top of Kubernetes as easy as possible, while preserving configurability as well as making the configuration Kubernetes native.

#### Logging

Q: How to get the central logs from POD?

A: This architecture depends upon application and many other factors. Following are the common logging patters

- Node level logging agent
- Streaming sidecar container
- Sidecar container with logging agent
- Export logs directly from the application

In our setup, filebeat and journalbeat are running as daemonset. Logs collected by these are dumped to kafka topic which are eventually dumped to ELK stack. 

Same can be achieved using EFK stack and fluentd-bit.  
