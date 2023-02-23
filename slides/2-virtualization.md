## Virtualization and Containerization

Note: One of the key pain points we talked about of Developers and Operations was the innability of simulating the production and environment and replicate it. As a Developer probably used a different environment to develop it how can he be sure that it will work on a different machine with maybe different libraries, programs, kernel or another form of hidden state. When handling a JAR, a non-standalone binary or any other artifact, we can have trouble on guaranteeing that it will work.
Both virtualization and containerization are tools that helps us to encapsulate all the surrounding environment necessary to our application and make it more reproducible. Given that we have the same server, running a VM or a container on it would just work as it had all things necessary to make it work. 

Although they might sound the same at the first glance, the are different, take a look.


## Virtual machines

![](https://miro.medium.com/v2/resize:fit:1400/0*uOG3TpWM2BlBYkbg)

Note:
Virtual machines encapsulate whole Operational System, they must be run by an abstraction layer called Hypervisor. Hypervisor can be run directly at bare metal, on what we call Type 1 Hypervisor or on top of a Host OS called Type 2 Hypervisor. If you had played with a virtual machine at home, you are probably running it on a Type 2 Hypervisor. If you had instantied an EC2 on AWS, you are probably running with a Type 1 Hypervisor behind the scenes.
It's important to notice, that not only virtual machine don't only act as a way to encapsulate the state for an application to run but they also provide cloud providers with an abstraction to share the same physical server to multiple applications or customers, so you don't need to pay for the whole server blade.


![](https://www.racksolutions.com/news//app/uploads/Rack-server-and-blade-server-together.jpg)


## Containers

![](https://codeahoy.com/img/dockercontainers/containers.png)

Note:
Containers are different. They don't encapsulate an entire operational system and are very lightweight. This happens because they share the same underlying kernel. The only abstraction is the container runtime on top of the operating system. We can't run on a Linux machine a container running a Windows application and a container running Redis on linux. You might ask, hey, but I'm running WSL/WSL2 right now! Running Linux containers on my Windows just fine!
Welp, what is happening under the hood is Windows managing a very lightweight Virtual Machine running Linux, which there runs a container runtime.


## Containers vs Virtual Machines

<!-- .slide: data-background-color="white"  --> 
![virtualization](https://wac-cdn.atlassian.com/dam/jcr:92adde69-f728-4cfc-8bab-ba391c25ae58/SWTM-2060_Diagram_Containers_VirtualMachines_v03.png?cdnVersion=804)

Note:
Now, let's compare them side by side! (Explains the diagram)


#### Virtual machines
- Full isolation and security, harder to contaminate neighboring virtual machines
- Slower to iterate on, because they encompass a full stack system. 
- High storage size 
- Slower to spin


#### Containers

- Lightweight, thus very fast to modify and iterate on
- Robust ecosystem
- Security risks concerning shared host exploits
- Faster to spin

Note:
We don't have a single container runtime available. Even docker was not the first. The first one was called Linux Container (LXC) that docker uses under the hood. Popular runtimes today besides docker are: containerd, CRI-O and RKT. We will explore Docker as it's the most known and used container runtime.
