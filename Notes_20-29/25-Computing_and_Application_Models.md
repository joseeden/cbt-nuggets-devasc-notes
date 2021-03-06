
# 25 - Computing and Application Models
____________________________________________________________

<!-- 2021-01-14 04:33:51 -->

**VIRTUALIZATION**
Carving out a portion of the computing resource to create a virtual environment, which can host its own operating system.


**BARE METAL** 
Physical computer components, Server sitting on a datacenter with enormous RAM, resources, etc.

**HYPERVISOR**
Sofware that manages virtual environments on the bare metal server/computer. Example, HyperV, VirtualBox, VMware.

There are 2 types of Hypervisors: Type 1 and Type 2.

&nbsp;&nbsp;&nbsp;&nbsp;**TYPE 1 HYPERVISOR** 
&nbsp;&nbsp;&nbsp;&nbsp;There is no OS. It's like a VMware running directly on a computer, hosts other VMs.

&nbsp;&nbsp;&nbsp;&nbsp;**TYPE 2 HYPERVISOR**
&nbsp;&nbsp;&nbsp;&nbsp;Runs inside the OS of the computer. Example is HyperV. Here you first need Windows on a baremetal
                    computer and hypervisor runs inside that Windows Environment
<br>

**CONTAINER**
A bit similar with VMs, but are completely different. They are another abstraction layer above VMs.

You can have multiple containers running inside a VM.
Containers are just like isolated execution environment.
More portal and lightweight. but requires more overhead to manage and maintain it.

To manage containers, you need a piece of software called **Docker**. Containers are isolate with one another.

**COMPARISON**

    Virtual machines    
    share the underlying HW of a bare metal computer with the other VMs.

    Containers          
    share the underlying kernel/OS of virtual machines.

<br>

_______________________________________________________

## DOCKER ##

Management tool for containers. This is not a containerization software. The containerization software is built-in to the OS.

Docker takes a container and bundles it up to a single file in your OS. This makes it easy to handle the file - duplicate it, send it to cloud.
______________________________________________________________

## EDGE COMPUTING ##

Architectural approach, moving data processing and storage is moved closer to where it is collected and used, i.e the Edge!

One thing to consider is, edge computing is not a binary thign - either centralized or all the way out.

There are different layers in the network and there are a lot of devices in the middle. It should be discussed how far out  do we push the data.

**PROS:**

- Speed/Latency     - higher speed, lower latency
- Privacy           - data is not sent to centrals servers, it stays on he device where it is collected
- Resiliency        = if one location goes down, the other locations are still running
- Scalability       - system is designed to add or remove

**CONS:**

- resources         - edge devices will need to be able to handle resource-intensice operations
- Infra complexity  - if you need more processing power, you'll need more CPUs, storage, etc.
- Distribution of 
    Security, knowledge

______________________________________________________________

## CLOUD COMPUTING ##

Leveraging on-demand resources and economies of scaleto deploy computing solutions. Instantly deploy on demand.

______________________________________________________________

## DEPLOYMENT METHODS ##

Cloud computing relies on accessible infrastructure.

1.  **PUBLIC CLOUD**
    Leverage publicly available cloud infra over the internet.
    Cloud providers ar epopular for having different geographic locations, plus
    they have more mature and robust software capabilities and tools to itnerface ith those datacenter.
    <br>

2.  **PRIVATE CLOUD **
    Leverage privately-owned infra within an organization.
    Private clouds tend to be smaller than public clouds.
    More on the requirement for security. 
    Things can be also a bit mroe slower in deploying in private clouds.
    <br>

3.  **HYBRID DEPLOYMENT**
    Combination of public and private


