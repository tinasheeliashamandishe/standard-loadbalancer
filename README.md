<h1>Azure Load Balancer : Standard</h1>

<h2>Description</h2>
This lab will show how a Standard Azure Loadbalancer works.<br/><br />

Azure Load Balancer is a networking service provided by Microsoft Azure, designed to distribute incoming network traffic across multiple resources, such as virtual machines (VMs), virtual machine scale sets, or application gateways. It enhances the availability and reliability of applications by ensuring that they are not overloaded and by providing redundancy in case of failures.
<br /><br />
Key features of Azure Load Balancer include:
<br /><br />
<b>Traffic Distribution:</b> It evenly distributes incoming network traffic across multiple resources to ensure that no single resource becomes overwhelmed.<br />
<b>High Availability:</b> By spreading the workload across multiple resources, Azure Load Balancer enhances the availability of applications and services. If one resource becomes unavailable, traffic is automatically rerouted to the remaining healthy resources.<br />
<b>Health Monitoring:</b> Azure Load Balancer continuously monitors the health of backend resources to ensure that traffic is only directed to healthy instances. If a resource fails health checks, it is temporarily removed from the load balancer rotation until it becomes healthy again.<br />
<b>Session Persistence:</b> It supports session persistence, ensuring that requests from the same client are directed to the same backend resource, which is essential for maintaining session state in stateful applications.<br />
<b>Layer 4 and Layer 7 Load Balancing:</b> Azure Load Balancer supports both Layer 4 (transport-level, such as TCP and UDP) and Layer 7 (application-level, such as HTTP and HTTPS) load balancing, providing flexibility to cater to various application requirements.<br />
<b>Inbound NAT Rules:</b> It allows inbound network address translation (NAT) rules to direct traffic from specific ports of the load balancer to specific ports of backend resources, enabling scenarios such as port forwarding.<br /><br />
Azure Load Balancer plays a crucial role in building scalable and highly available applications and services in the Azure cloud environment.
<br/><br/>

<h2>Environments Used </h2>

- <b>Packet Tracer</b>

<h2>Lab walk-through:</h2>

<p align="center">
<h4>Lab Topology:</h4>
In this Lab there are 2 virtual machines, on is running IIS and the other is running NGINX. They do not have public IP addreses. The loadbalancer sists infront of them with 2 public IP addresses.<br />
The loadbalancer will be used to reach the VMs.
  <br/>
<img src="https://i.imgur.com/fVLWRPj.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />

<h4> Step 1:</h4>
Deploy 2 virtual machines. Install IIS and NGINX respectively<br />
<img src="https://i.imgur.com/bxP8k1C.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br/>
<img src="https://i.imgur.com/B8cp1pf.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br/>
<br />

<h4>Step 2:</h4> 
Create a NSG for the subnet and add an HTTP incoming rule to it.<br />
<img src="https://i.imgur.com/nLxF7gD.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br/>
<img src="https://i.imgur.com/uRpSnrX.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br/>
<br />

<h4>Step 3:</h4> 
Deploy a Standard Load Balancer resource.<br />
Configure the font-end IPs, Backend pools, Heart probes and Loadbalancing rules.<br />
<img src="https://i.imgur.com/fNqGYOt.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br/>
<br />

<h4> Step 4:</h4> 
Verify that the front-end IPs has been Configured.<br />
<img src="https://i.imgur.com/vm9LRIh.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br/>
<br />

<h4> Step 5:</h4> 
Go onto the front-end IP.<br />
As can be seen the Loadbalancer is able to direct you to both Virtual machines using the provided IP addresses.<br />
<img src="https://i.imgur.com/Ya3ivYF.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br/>
<img src="https://i.imgur.com/RhMKQWO.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br/>
<br />
