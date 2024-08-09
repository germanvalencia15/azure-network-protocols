<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, RDH, DNS, HTTP/S, ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 11
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

- Create a resource group in Microsoft Azure.
- Create two virtual machines in Azure.  One vm running Windows and the second vm running Linux. 
- Remote connect to Windows vitual machine and install Wireshark.
- Open Wireshark and filter for ICMP traffic. 

<h2>Actions and Observations</h2>

<p>

![image](https://github.com/user-attachments/assets/7b6985fe-5078-4bc1-a459-12af59a01cb3)


</p>
<p>
From the Microsoft Azure portal homepage I went into resouce groups and and created a new resource group for this lab. 
</p>
<br />

<p>

![Screenshot 2024-08-09 110015](https://github.com/user-attachments/assets/534a90c1-bd27-4846-b164-e28e9e502cf4)

</p>
<p>
Above I created two virtual machines in Azure.  One vm is running Windows and the second vm is running Linux.  Only one virtual network was created for both VMs and subnets were created automatically.  
</p>
<br />

<p>

![Screenshot 2024-08-09 112225](https://github.com/user-attachments/assets/f4a21343-cde4-41dc-96f0-caa09b936609)

</p>
<p>
In this next step I connected to Windows vm using Remote Desk top.  Once inside of vm1 I downloaded and installed wireshark. 
</p>
<br />
