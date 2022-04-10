# LINUX Administration

  1. [Simple Linux Questions](#simple)
  1. [Medium Linux Questions](#medium)
  1. [Hard Linux Questions](#hard)
  1. [Expert Linux Questions](#expert)
  1. [Networking Questions](#network)



####[[⬆]](#toc) <a name='simple'>Simple Linux Questions:</a>

* What is the name and the UID of the administrator user?
  - root, 0

* How to list all files, including hidden ones, in a directory?
  - ls -a or find .

* What is the Unix/Linux command to remove a directory and its contents?
  - rm -R

* Which command will show you free/used memory? Does free memory exist on Linux?
  - free
  - Sure exists, but the Linux kernel creates file caches in ram, so when we see the output from free command, sometimes can show us that we are without memory but this memory is cached by the OS.

* How to search for the string "my konfi is the best" in files of a directory recursively?
  - grep -Rin "my konfi is the best" /folder

* How to connect to a remote server or what is SSH?
  - ssh user@server - simple way
  - SSH (secure shell) it's a cryptographic network protocol, used for remote login to computer systems by users.

* How to get all environment variables and how can you use them?
  - env, set or printenv, will show every variable that login session, we can use setting as variables ex.: TEST=something or using export the variable will be global (can be used by all system users)

* I get "command not found" when I run ```ifconfig -a```. What can be wrong?
  - your PATH variable doesn't have the full path for the ifconfig command.

* What happens if I type TAB-TAB?
  -  It depends which program the user is trying to complete

* What command will show the available disk space on the Unix/Linux system?
  - df -h

* What commands do you know that can be used to check DNS records?
  - dig +trace
  - nslookup
  - whois
  - host

* What Unix/Linux commands will alter a files ownership, files permissions?
  - chmod, chown, chattr

* What does ```chmod +x FILENAME```do?
  - Add a execute permission to a file for all users

* What does the permission 0750 on a file mean?
  - Add a permission to the owner of the file write, execute and read, the group of the owner execute and read, and others do nothing

* What does the permission 0750 on a directory mean?
  - Add a permission to the owner of the folder, create, get access and list the directory files,for the group of the owner only enter and list the directory, and nothing for others.
  - +r - User can list the files
  - +w - User can create a file inside the directory
  - +x - User can get into the folder

* How to add a new system user without login permissions?
  - useradd username -s /bin/false

* How to add/remove a group from a user?
  - usermod -a -G groupname username #to add a user in a new group
  - usermod -G [all groups that you want the user into] username #You don't remove the user from a group, you add the user in all groups that this user is suppose to be.
  - newgrp <GroupName> - Updates shell session with new group permissions

* What is a bash alias?
  - It's a shortcut for some bash command

* How do you set the mail address of the root/a user?
  - creating a file called .forward in the user folder
  - editing the file /etc/aliases

* What does CTRL-c do?
  - send a SIGINT to the terminal (it's a polite kill)

* What is in /etc/services?
  - A mapping for services and ports, when a service call a function getportbyname() usually this function goes in this file to check.
  - Example the command netstat or ss without the -n parameter

* How to redirect STDOUT and STDERR in bash? (> /dev/null 2>&1)
  - 1> redirect the STDOUT
  - 1>> redirect the STDOUT in append mode
  - 2> redirect the STDERR
  - 2>> redirect the STDERR in append mode
  - &> redirect both STDERR and STDOUT
  - &>> redirect both STDERR and STDOUT in append mode
  - 2>&1 redirect STDERR to STDOUT

* What is the difference between UNIX and Linux.
  - Linux it's a UNIX "clone" using the same POSIX(Portable Operating System Interface) standards, but UNIX it's a brand, has different copyrights and tools.

* What is the diference between Telnet and SSH?
  - SSH it's encrypted and telnet isn't.
  - Telnet can ommit authentication
  - SSH adds overhead to the bandwidth

* Explain the three load averages and what do they indicate. What command can be used to view the load averages?
  - The three load averages indicate the processor usage estimated in 1 minute, estimated in 5 minutes and 15 minutes.
  - top or uptime

* Can you name a lower-case letter that is not a valid option for GNU ```ls```?
  - z

####[[⬆]](#toc) <a name='medium'>Medium Linux Questions:</a>

* What do the following commands do and how would you use them?
 * ```tee```
  - copies the STDOUT to a file, but continues to show the STDOUT.

 * ```awk```
  - awk it's a programming language designed for text processing.

 * ```tr```
   - tr or translate, it's a command to substitute characters.

 * ```cut```
   - cut is a command for text processing and extracts a portion of a text

 * ```tac```
  - tac it's a reverse cat, pritting the file bottom to up.

 * ```curl```
  - curl or cURL is a tool to transfer data from or to a server, using one of the supported protocols. cURL can be called a CLI browser, you can use to authenticate, change the HEADER, and do a lot of stuffs with it.

 * ```wget```
  - wget is a tool for retrieving files using HTTP, HTTPS , or FTP.

 * ```watch```
  - Watch it's a tool that runs a specified command repeatedly and displays the result on standard output.

 * ```head```
   - It's a command that shows the first lines of a file, the default it's 10 lines

 * ```tail```
   - It's a command that shows the last lines of a file, the default it's 10 lines

* What does an ```&``` after a command do?
  - Makes the command run in a background sub shell, and becomes a job.

* What does ```& disown``` after a command do?
  - disown control jobs that are running in the system, without any paramenter or ID removes the last job on the job table.

* What is a packet filter, and how does it work?
  - Packet filter it's the process of passing or blocking packets at a network interface based on source and destination address, port or protocols. The packet filter examines, the header of every packet who passed through and based in the rules, ACCEPT, DROP or REJECT the packet, it's well know as firewall.

* What is Virtual Memory?
  - Virtual memory it's the amount of memory available for the system, physical memory + swap memory (hard disk memory).

* What is swap and what is it used for?
  - Swap it's a disk partition used by the Linux when the physical memory is full, if the system needs more memory resources some inactive pages are copied to swap, it was a common way to increase the computer/server memory using the disk.

* What is an A record, an NS record, a PTR record, a CNAME record, an MX record?
  - A record stands for address, indicates an IP address for a domain
  - NS stands for Name Server record indicates which DNS server is authoritative for that domain ( Where the actual DNS entries are)
  - CNAME stands for canonical name and servers to make one domain to another domain name.
  - MX stands for mail exchange, it's a list of mail exchange servers used by the domain.

* Are there any other RRs and what are they used for?
  - Yes.
  - PRT record stands for pointer record  and maps an IPV4 address to a CNAME
  - SOA record stands for State of Authority and is easily one of the most important DNS records because stores information like when the domain was last updated.
  - SRV record stands for Service Record, is a record that specifies hostname and port number for a specific service, it can be used for service discovery.
  - TXT record stands for Text Information, used by various purposes, as domain ownership for example.

* What is a Split-Horizon DNS?
  - It's the feature/configuration of the DNS server answer a different resolution to a query based on the source of the query. A common use it's when the DNS server needs to diferentiate internal and external queries, for the same domain.
   We can use views to configure this.

* What is the sticky bit?
  - It's a permission bit that is set on a file or a directory  that let only the owner of the file/directory or the root user to delete or rename the file.

* What does the immutable bit do to a file?
  - It makes the file immutable, any user can change the state of the file or create hard links.

* What is the difference between hardlinks and symlinks? What happens when you remove the source to a symlink/hardlink?
  - All files in the linux filesystem are a link to a inode, a hard link is a new link to the same inode (if you remove or rename the old or the new link, the file will be intact, but any change in the data on the inode is reflected in all files that refer to that inode), the file system will only delete the inode if you don't have any link for this inode. Because of this characteristic a hardlink only works on files that are in the same file system.

  - A softlink, it's a link that points the link from the inode, so it's a link from a link if the first link change the name or be deleted, the soft link will break, but can be used between differents filesystems.

* What is an inode and what fields are stored in an inode?
  - Each object in the filesystem is represented by a inode that stores all the information about the file, like file type, permissions, owner, group, file size, file access, change and modification time (never birth time), file deletion time, number of links, extended attributes. Each inode has a unique number and it can acessed using ``` stat filename ``` 

* How to force/trigger a file system check on next reboot?
  - Create a file named forcefsck in the root folder

* What is SNMP and what is it used for?
  - SNMP stands for simple network monitoring protocol, it's a protocol to monitor devices, works in the application layer, has 3 versions now, they are not compatible between each other, and V3 introduced encryption. Messages are transported via UDP.

* What is a runlevel and how to get the current runlevel? 
  - Runlevel it's a preset operational system state, so based in this level, the OS starts the corresponding services, or scripts. To get the current runlevel uses the command runlevel, or `who -r`

* What is SSH port forwarding?
  - SSH Port forwarding it's a way to create a tunnel between your machine in a destination using ssh.

* What is the difference between local and remote port forwarding?
  - Local port forwarding creates a tunnel between a local server and a local client, a remote port uses a local server but with internet IP address to connect a internal service that doesn't have access in the internet.

* What are the steps to add a user to a system without using useradd/adduser?
  - Edit `/etc/passwd` with the new username, configure the home, and shell
  - Edit `/etc/groups` add this new username to some groups
  - Create the user home folder and set the right permissions
  - Reset the user password with `passwd username`

* What is MAJOR and MINOR numbers of special files?
  - The MAJOR number will set to the kernel with kind of device it is, and MINOR number will set a special characteristics of the device, example if a machine have 2 disks, the MAJOR number will be the same for both, but the MINOR doesn't.

* Describe the mknod command and when you'd use it.
  - mknod command creates a new device in `/dev` but actually udev creates automatically each device, if something very terrible happen we can recreate some devices using mknod to fix or make some backup.

* Describe a scenario when you get a "filesystem is full" error, but `df` shows there is free space.
  - When a filesystem it's out of inode, it can happen when you have a huge amount of small files, in a small filesystem. `df -i` will show.

* Describe a scenario when deleting a file, but 'df' not showing the space being freed.
  - when a process it's still appending that file. We can use `lsof` to check it.

* Describe how 'ps' works.
  - the ps command read files from /proc and the content of these files are generated by the kernel.

* What happens to a child process that dies and has no parent process to wait for it and what’s bad about this?
  - creates a zombie process, one zombie process it's not a big problem, but each process uses a little size of ram, and uses a PID that's a finite number of it.

* Explain briefly each one of the process states and all signals
  - CREATED or NEW STATE, in this moment the process wait the admission to the ready state, by the scheduler
  - RUNNING/RUNNABLE (R) the process has been loaded into main memory and is awaiting execution by the CPU, or it's using CPU core right now
  - SLEEPING a sleeping process is a process waiting for a resource to be available, I/O operation to complete for example, or an event to happen. There is two states of SLEEPING process
    - Interrruptible Sleep (S) - Process that can be terminated before the wake up condition is fulfilled without any consequences.
    - Uninterruptible Sleep (D) - Process that can't be killed, in the example of I/O operation, the act the process it's in uniterruptible sleep (D) until a the I/O operation to complete and wake up.
  - STOPPED (T) - A process becomes stopped when it receives the SIGSTOP signal, when stopped the process execution is suspended and only signals it will handle are SIGKILL and SIGCONT
  - Zombie (Z) it's a state after completing the execution or being explicitly killed, but the process remains as a zombie until the parent process call the wait system call to read its exit status, and finally ending the process lifetime.
  - Process SIGNALS are one of the ways process communicate among themselves and with the kernel. Exceptionally SIGKILL and SIGSTOP signals cannot be handled or blocked.
    - SIGTERM - the default signal sent by kill command, Asks the process to terminate voluntarily
    - SIGKILL - unlike SIGTERM, forces the process to terminate, can't be blocked or handled
    - SIGSTOP - suspend the process execution, putting in stopped state. In this state, the process will do nothing but accept SIGKILL or SIGCONT.
    - SIGSTP - almost identical to SIGSTOP, the only difference is it can be blocked or handled, this is the signal sent when you type `<ctrl>+z` in the terminal
    - SIGCONT - if a process is in stopped state, it will put it back in the RUNNING/RUNNABLE state and resume it execution. If the process is in any other state, it's silently ignored.
    - SIGINT - generated when the user type `<ctrl>+c` in the terminal, it interrupts the current command processing and wait for user's next command.
    - SIGQUIT - generated when eht user type `<ctrl>+\` in the terminal, normally it will force the process to produce a core dump and terminate.
    - SIGALARM - signal used to wake up sleeping process, normally scheduled by alarm system call.
    - SIGCHLD - sinal send from a child process to its parent process when its state changes.
    - SIGHUP - the signal indicates the terminal handling the process has been disconnected and/or parent process terminated. To run a process that won't terminate when the terminal disconnects, you can start it using the command `nohup`.

* How to know which process listens on a specific port?
  - `lsof -i :$PORT` or `netstat -lp | grep $port` or `ss -lp | grep $port`

* What is a zombie process and what could be the cause of it?
  - A zombie process is a process whose execution is completed but it still has an entry in the process table. Zombie process usually occurs for child process, as the parent process still needs to read its child exit status.

* You run a bash script and you want to see its output on your terminal and save it to a file at the same time. How could you do it?
 - Use the tee command
 - `script | tee file`

* Explain what echo "1" > /proc/sys/net/ipv4/ip_forward does.
 - Disable ipv4 ip_forward function from the kernel, as well the IPV4 routing function

* Describe briefly the steps you need to take in order to create and install a valid certificate for the site https://foo.example.com.
  - Create a key file
  - Uses this key file to create a csr file
  - Send this csr file to a ssl certificate provider
  - Get the crt from the certificate provider with the CA chain and configure into the webserver
  - Or you can use certbot to simplify.

* Can you have several HTTPS virtual hosts sharing the same IP?
  - Yes using virtualhosts, but the client needs to support http/1.1, to use name-based virtual host configuration.

* What is a wildcard certificate?
  - It's a certificate that can be used by differents hostnames from a single domain.

* Which Linux file types do you know?
  - Regular file
  - Directory file
  - Special files
    - Block file
    - character file
    - named pipe file
    - symbolic link file
    - socket file

* What is the difference between a process and a thread? And parent and child processes after a fork system call?
  - A fork it's an identical process as the parent but with new PID, it has a own memory share, and runs independently from the parent. A thread it's a lightweight process and usually it's just a CPU state with the process containing the remainings. A threads require less overhead then forking or spawning a new process, because doesn't have a new system virtual memory space and environment.
  - Both child and parent process have different PIDs, neither process access the variables of each other, the child process ctime, uptime, stime, cutime and cstime subrotines are set to 0.

* What is the difference between exec and fork?
  - A fork in a simple way, it's a process copy only changing the pid and resource limits, a exec it's a call that basically replaces the entire current process with a new program. It loads the program into the current process space and runs it from the entry point. Example, when we call the find command, our bash forks itself, and in this new fork context, uses exec call to execute the find program.  

* What is "nohup" used for?
  - It's used to create process that are independent from user login, starting a process with nohup it's telling the process to ignore SIGHUP calls, that the signal sent by the kernel when the parent shell is closed.

* What is the difference between these two commands?
 * ```myvar=hello```
 * ```export myvar=hello```
 - The first one create the variable only in the user context, the second in a global context, so this variable can be used by all users.

* How many NTP servers would you configure in your local ntp.conf?
  - 4 it's minimum recommended by RedHat

* What does the column 'reach' mean in ```ntpq -p``` output?
  - It's a octal number, that show the last 8 transactions with the ntp server, this number is a FIFO log, so if the same packet doesn't arrive (it's UDP), this number can be different based in the order of the checks.

* You need to upgrade kernel at 100-1000 servers, how you would do this?
  - I would be using Ansible, but before I would test in a controled group to check if something bad can happen.

* How can you get Host, Channel, ID, LUN of SCSI disk?
  - `cat /proc/scsi/scsi`

* How can you limit process memory usage?
  - Calling the program with limit command, or set the ulimit in the console, or in the /etc/security/limits.d, or in the systemd init script.

* What is bash quick substitution/caret replace(^x^y)?
  - `sed -e 's/^x/^y/g'`

* Do you know of any alternative shells? If so, have you used any?
  - I use zsh, it's 100% bash compatible

* What is a tarpipe (or, how would you go about copying everything, including hardlinks and special files, from one server to another)?
  - It's a way to copy a directory to a server from another preserving permissions and the files, usually I don't copy files from a server to another, I use automation to do the job to recreate the server for me, but if I really need to copy, we could use a tarpipe, or dd.

####[[⬆]](#toc) <a name='hard'>Hard Linux Questions:</a>

* What is a tunnel and how you can bypass a http proxy?
  - We can create a ssh tunnel with ssh -R and redirect the http proxy to a server that has access to the internet.

* What is the difference between IDS and IPS?
  - IDS detect the problem inspecting the packet header and payload and creates a log.
  - IPS detect the problem inspecting the packet header and payload and drops the packet if finds something problematic, based in some pre defined rules.

* What shortcuts do you use on a regular basis?
  - `ai package` - `sudo apt install package`
  - `ll` - `ls -lha`
  - `gitcm` - `git commit -m`
  - `gl` - `git pull`
  - `gp` - `git push`
  - `..` - `cd ..`
  - `...` - `cd ../..`
  - `....` - `cd ../../../`

* What is the Linux Standard Base?
  - It's a joint project projected by several Linux distributions under the organizational structure of the Linux Foundation to standardize the sofware system structure, including filesystem hierarchy.

* What is an atomic operation?
  - Atomic operations are program operations that run until completion independently from any other process.

* Your freshly configured HTTP server is not running after a restart, what can you do?
  - I would try to see the logs and check what's the problem. `jounalctl -xe` `systemctl status httpd`

* What kind of keys are in ~/.ssh/authorized_keys and what it is this file used for?
  - Public keys, they are used to authenticate users in the server.

* I've added my public ssh key into authorized_keys but I'm still getting a password prompt, what can be wrong?
  - The permission for authorized_keys file, and .ssh folder, as the path from authorized_keys file needs to be /home/user/.ssh/authorized_keys and right spelled, or your private key has the wrong permission.

* Did you ever create RPM's, DEB's or solaris pkg's?
  - yes using fpm, and using dpkg or rpm.

* What does ```:(){ :|:& };:``` do on your system?
  - creates a forkbomb

* How do you catch a Linux signal on a script?
  - using the command `trap` inside the script

* Can you catch a SIGKILL?
  - No, by security proposes

* What's happening when the Linux kernel is starting the OOM killer and how does it choose which process to kill first?
  - OOM will kill the process that will free more memory and the least important for the OS.

* Describe the linux boot process with as much detail as possible, starting from when the system is powered on and ending when you get a prompt.
  - BIOS/UEFI
    - BIOS performs startup based in the hardware, POST ( Power On Self Test) processs to initiallize the hardware, after complete, and calls the bootloader.
  - bootloader
    - The bootloader (GRUB2) present options to the user select, GRUB supports unix-like OS, and chain-load Windows OS, and loads the kernel into memory and supplies it with some parameters.
  - kernel
    - The kernel will decompress itself and will setup essential hardware and memory paging, and calls start_kernel() function, and it will perform the majority of system setups like device and driver initialization, scheduler, idle process and then starts separately in the user space the init process (pid 1).
  - init
    -The init it's scripts executed by shell (sysV, runit) or configuration files that are executed by binaries (upstart, systemd), init has specific levels, that are passed as variables at the call, with consists of specifics set of daemons. These will provide various non-operating system services and structures and form the user environment.
  - User environment
    - The typical desktop environment begins with a daemon that calls everything needed.
  To shutdown, it's the inverse, the kernel kills every process, and shutdown.

* What's a chroot jail?
  - Chroot jail it's a way to isolate a process and its children from the rest of the system. The idea is that you create a directory tree where you copy or link in all the system files needed for a process to run, usually we use bind to mount some folder inside a chroot.

* When trying to umount a directory it says it's busy, how to find out which PID holds the directory?
  - lsof directory

* What's LD_PRELOAD and when it's used?
  - LD_PRELOAD it's a variable that can be used to load some library before the default C library, can be used to test a new version for a library, or for development proposes.

* You ran a binary and nothing happened. How would you debug this?
  - strace binary, and see what's happening.

* What are cgroups? Can you specify a scenario where you could use them?
  - Cgroups are a Linux kernel feature that allow limit the resource use for a group of process(CPU, memory, disk I/O). A scenario to use could be to test a software in a physical machine that has a big hardware, and make this software run a minimum configuration, a very common sofware that uses cgroups it's in contairners ( docker, crio).


####[[⬆]](#toc) <a name='expert'>Expert Linux Questions:</a>

* A running process gets ```EAGAIN: Resource temporarily unavailable``` on reading a socket. How can you close this bad socket/file descriptor without killing the process?
  - using gdb, attach the gdb in the process and close the file descriptor or socket that is problematic, and detach.


####[[⬆]](#toc) <a name='network'>Networking Questions:</a>

* What is localhost and why would ```ping localhost``` fail?
  - Localhost it's the internal interface in Linux, that some programs can use to talk to each other inside the server. The ping will fail if the lo interface is down, or if we don't resolve localhost in our /etc/hosts file or some firewall rule is dropping ICMP packets or blocking lo interface.

* What is the similarity between "ping" & "traceroute" ? How is traceroute able to find the hops.
  - Both use ICMP (Internet control message protocol) packets to archive their proposes, but traceroute sends the packets gradually increasing the TTL value, starting with TTL 1. The first router  receives the packet, decrements the TTL value and drops the packet because the TTL has zero. The router sends an ICMP Time Exceeded message back to the source.


* What is the command used to show all open ports and/or socket connections on a machine?
  - `lsof -i`
  - `netstat -a`
  - `ss -a`

* Is 300.168.0.123 a valid IPv4 address?
  - no

* Which IP ranges/subnets are "private" or "non-routable" (RFC 1918)?
  - 10.0.0.0/8
  - 192.168.0.0/16
  - 172.16.0.0/16

* What is a VLAN?
  - It's a virtual lan created to separate networks inside a switch, making the broadcast domain shorter, and for security proposes. Works in the network layer (OSI Layer 2)

* What is ARP and what is it used for?
  - It's a layer 2 protocol that maps IP address to MAC address.

* What is the difference between TCP and UDP?
  - TCP ( Transmissions control protocol ) and UDP ( User Datagram Protocol ), both works in the layer 3 of the OSI model, and are different methods to send information across networks, or Internet. TCP is used in scenarios when reliability is important, and is used by the majority of layer 7 protocols, like HTTP, FTP, SMTP. TCP is connection-oriented ( after estabilishes the connection between two devices, maintains until the transfer process finishes), and uses a process called three-way handshake ( SYN, SYN-ACK, ACK).. 
  - UDP it's a connectionless protocol ( doesn't estabilish a connection before hand) it's much simple and used in situations when data loss is acceptable, because doesn't guarantee all data is successfully transferred.

* What is the purpose of a default gateway?
  - The default gateway it's the way to get in other networks.

* What is command used to show the routing table on a Linux box?
 - route
 - netstat -r
 - ip route list
 - ip r

* A TCP connection on a network can be uniquely defined by 4 things. What are those things?
 - remote-ip-address
 - remote-port
 - source-ip-address
 - source-port

* When a client running a web browser connects to a web server, what is the source port and what is the destination port of the connection?
  - source port it's dynamic based on net.ipv4.ip_local_port_range defined between 32768 - 61000, destination port 80 or 443.

* How do you add an IPv6 address to a specific interface?
  - using ip -6 addr command, or using ifconfig ip inet6, or editing the OS file for network interfaces.

* You have added an IPv4 and IPv6 address to interface eth0. A ping to the v4 address is working but a ping to the v6 address gives yout the response ```sendmsg: operation not permitted```. What could be wrong?
  - can be a firewall rule

* What is SNAT and when should it be used?
  - SNAT stands for Source Network Address Translation - changes the source address in IP header of a packet. The typical usage is to change the private address/port to a public address/port for packets leaving the network.

* Explain how could you ssh login into a Linux system that DROPs all new incoming packets using a SSH tunnel.
  - We could login using some DRAC interface if the machine it's physical, or we can use the libvirt, or vmware console if virtual, or aws console.

* How do you stop a DDoS attack?
  - You try to block the source address of the attack, or we use some CDN.

* How can you see content of an ip packet?
  - capturing the packet with tcpdump, and opening with wireshark.