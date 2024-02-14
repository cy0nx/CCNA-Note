###  Servers before Virtualization  

● Before virtualization, there was a one-to-one relationship between a physical server and an operating system.

● In that operating system, apps providing services such as a web server, email server, etc. would run.

● One physical server would be used for the web server, one for the email server, one for the database server, etc.  
![1445-08-04 23_48_31-Day 54 Slides - Virtualization   Cloud pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/14dc3cd5-42b9-4608-a27b-52486187627e)  
<br>


###  Virtualization (Type 1 Hypervisor)  

● Virtualization allows us to break the one-to-one relationship of hardware to OS, allowing multiple OS’s to run on a single physical server.

● Each instance is called a VM (Virtual Machine).

● A **hypervisor** is used to manage and allocate the hardware resources (CPU, RAM, etc) to each VM.

● Another name for a hypervisor is VMM (Virtual Machine Monitor).

● The type of hypervisor which runs directly on top of the hardware is called a **Type 1** hypervisor.  
→ Examples include VMware ESXi, Microsoft Hyper-V, etc.

● Type 1 hypervisors are also called bare-metal hypervisors because they run directly on the hardware (metal).  
→ Another term is native hypervisor

● This is the type of hypervisor used in data center environments.  
![1445-08-04 23_49_57-Day 54 Slides - Virtualization   Cloud pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/5bc38a65-f795-433e-8093-e5c454525038)  
<br>


###  Virtualization (Type 2 Hypervisor)  

● **Type 2** hypervisors run as a program on an operating system like a regular computer program.  
→ Examples include VMware Workstation, Oracle VirtualBox, etc.

● The OS running directly on the hardware is called the **Host OS**, and the OS running in a VM is called a **Guest OS**.

● Another name for a Type 2 hypervisor is hosted hypervisor.

● Although Type 2 hypervisors are rarely used in data center environments, they are common on personal-use devices (for example, if a Mac/Linux user needs to run an app that is only supported on Windows, or vice versa).  
![1445-08-04 23_51_34-Day 54 Slides - Virtualization   Cloud pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/7f76c34b-a202-4126-b41a-0e47d89a9bb9)  
<br>


###  Why Virtualization?  

● **Partitioning**: -Run multiple operating systems on one physical machine.  
 -Divide system resources between virtual machines.

● **Isolation**: -Provide fault and security isolation at the hardware level.  
 -Preserve performance with advanced resource controls.

● **Encapsulation**: -Save the entire state of a virtual machine to files.  
 -Move and copy virtual machines as easily as moving and copying files.

● **Hardware Independence**: -Provision or migrate any virtual machine to any physical server.  
![1445-08-04 23_53_23-Day 54 Slides - Virtualization   Cloud pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/92ef9a9d-4070-47fa-9d57-f566fcc5ba3e)  
<br>


###  Connecting VMs to the Network  

● VMs are connected to each other and the external network via a virtual switch running on the hypervisor.

● Just like a regular physical switch, the vSwitch’s interfaces can operate as access or trunk ports and use VLANs to separate the VMs at Layer 2.

● Interfaces on the vSwitch connect to the physical NIC (or NICs) of the server to communicate with the external network.  
![1445-08-04 23_54_44-Day 54 Slides - Virtualization   Cloud pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/19ca6a53-9a62-4157-9d9a-9563f81bd96a)  
<br>


##  Cloud Services  

● Traditional IT infrastructure deployments were some combination of the following:

**On-Premises**  
→All servers, network devices, and other infrastructure are located on company property.  
→All equipment is purchased and owned by the company using it.  
→The company is responsible for the necessary space, power, and cooling.

**Colocation**  
→Data centers that rent out space for customers to put their infrastructure (servers, network devices).  
→The data center provides the space, electricity, and cooling.  
→The servers, network devices, etc are still the responsibility of the end customer, although they are not located on the customer’s premises.  
<br>

###  The Five Essential Characteristics of Cloud  

● **On-demand self-service**  
The customer is able to use the service (or stop using the service) freely (via a web portal) without direct communication to the service provider.

● **Broad network access**  
The service is available through standard network connections (ie. the Internet or private WAN connections), and can be accessed through many kinds of devices.

● **Resource pooling**  
A pool of resources is provided by the service provider, and when a customer requests a service (for example creates a new VM), the resources to fulfill that request are allocated from the shared pool.

● **Rapid elasticity**  
Customers can quickly expand the services they use in the cloud (for example, add new VMs, expand storage, etc) from a pool of resources that appears to be infinite. Likewise, they can quickly reduce their services when not needed.

● **Measured service**  
The cloud service provider measures the customer’s usage of cloud resources, and the customer can measure their own use as well. Customers are charged based on usage (for example, X dollars per gigabyte of storage per day).  
<br>


### The Three Service Models of Cloud  

● In cloud computing, everything is provided on a ‘service’ model.

● There are a variety of services referred to as ‘______ as a Service’ or ‘__aaS’.

The three service models of cloud computing are:  
● **Software as a Service (SaaS)**  
The capability provided to the consumer is to use the provider’s applications running on a cloud infrastructure.  
Microsoft Office 365 is a popular example of SaaS.

● **Platform as a Service (PaaS)**  
The capability provided to the consumer is to deploy onto the cloud infrastructure consumer-created or acquired applications created using programming languages, libraries, services, and tools supported by the provider.  
Examples include AWS Lambda and Google App Engine.

● **Infrastructure as a Service (IaaS)**  
The capability provided to the consumer is to provision processing, storage, networks, and other fundamental computing resources where the consumer is able to deploy and run arbitrary software, which can include operating systems and applications.  
Examples include Amazon EC2 and Google Compute Engine.  

![1445-08-05 00_26_33-Day 54 Slides - Virtualization   Cloud pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/27bbe234-58b3-41db-b1c3-357b21041304)  
<br>


###  The Four Deployment Models of Cloud  

The four deployment models of cloud computing are:
● **Private cloud**  
Private clouds are generally only used by large enterprises.

Although the cloud is private, it may be owned by a third party.  
→ For example, AWS provides private cloud services for the American DoD.

Private clouds may be on or off premises.  
→ Many people assume that ‘cloud’ and ‘on-prem’ are two different things, but that is not always the case.

The same kinds of services offered are the same as in public clouds (SaaS, PaaS, IaaS), but the infrastructure is reserved for a single organization.  
<br>

● **Community cloud**  
This is the least common cloud deployment.

Similar to private cloud, but the infrastructure is reserved for use by only a specific group of organizations.  
<br>

● **Public cloud**  
This is the most common cloud deployment.

Popular public cloud service providers include:  
→ AWS (Amazon Web Services)  
→ Microsoft Azure  
→ GCP (Google Cloud Platform)  
→ OCI (Oracle Cloud Infrastructure)  
→ IBM Cloud  
→ Alibaba Cloud  
<br>

● **Hybrid cloud**  
This is basically any combination of the previous three deployment types.  
For example, a private cloud which can offload to a public cloud when necessary  
<br>


#  Cloud Services  

The five essential characteristics of cloud computing are:  
● **On-demand self-service**  
● **Broad network access**  
● **Resource pooling**  
● **Rapid elasticity**  
● **Measured service**  

The three service models of cloud computing are:  
● **Software as a Service (SaaS)**  
● **Platform as a Service (PaaS)**  
● **Infrastructure as a Service (IaaS)**  

The four deployment models of cloud computing are:  
● **Private cloud**  
● **Community cloud**  
● **Public cloud**  
● **Hybrid cloud**  
<br>


###  Benefits of Cloud Computing  

● **Cost**  
→CapEx (Capital Expenses) of buying hardware and software, setting up data centers etc. are reduced or eliminated.

● **Glocal Scale**  
→Cloud services can scale globally at a rapid pace. Services can be set up and offered to customers from a geographic location close to them.

● **Speed/Agility**  
→Services are provided on demand, and vast amounts of resources can be provisioned within minutes.

● **Productivity**  
→Cloud services remove the need for many time-consuming tasks such as procuring physical servers, racking them, cabling, installing and updating operating systems, etc.

● **Reliability**  
→Backups in the cloud are very easy to perform. Data can be mirrored at multiple sites in different geographic locations to support disaster recovery.  
<br>


###  Connecting to Cloud Resources 

![1445-08-05 00_33_57-Day 54 Slides - Virtualization   Cloud pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/caa2a3f9-67f7-402e-8788-3a7dcd15dfc2)
