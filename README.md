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
- Ubuntu Server 24.04

<h2>High-Level Steps</h2>

- Create a resource group in Microsoft Azure.
- Create two virtual machines in Azure.  One vm running Windows and the second vm running Linux. 
- Remote connect to Windows vitual machine and install Wireshark.
- Open Wireshark and filter for ICMP traffic.
- Obtain Ubuntu virtual machine private IP address and ping from Windows virtual machine.
- From Windows virtual machine ping www.google.com and observe traffic in Wireshark.
- Initiate perpetual ping from Windows virtual machine to Linux vm.
- Open Network Security Group for Linux vm and disable inbound ICMP traffic.
- Filter traffic by SSH only in WireShark

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

![image](https://github.com/user-attachments/assets/976af53f-ca71-429e-abae-5991b373d5df)


</p>
<p>
In this next step I opened Remote Desktop, connected to the windows virtual machine using it's public ip address. After gaining access to vm1 I downloaded and installed wireshark.  
</p>
<br />


![image](https://github.com/user-attachments/assets/1f4c82d8-1e4d-4503-a2a6-aa0de9106396)


In the image above from vm1 I opened Wireshark, filtered ICMP traffic only.  Then opened PowerShell and pinged Linux virtual machine 2. 



![image](https://github.com/user-attachments/assets/53268690-51ce-4df6-93ca-4ddf8adc7ef0)


Again in in the Windows virtual machine using Wireshark and PowerShell I was able to ping www.google.com and received a reponse.  You can see the traffic in Wireshark.  


![image](https://github.com/user-attachments/assets/115d802c-1abd-4d5b-8c63-718b2e665698)


Initiated perpetual ping from Windows vm to Linux vm.



![image](https://github.com/user-attachments/assets/1cfaad54-bc8c-4739-a136-663a6d4dcf1e)


Back in Azure I went into network security groups and added an inbound security rule for Linux vm and denied acces to all ICMP traffice.  You can see in the image abouve that traffic timed out.


![image](https://github.com/user-attachments/assets/a9492487-bb92-4c9a-a793-47b9cae12660)


Now by reversing the rule you can see that traffic has started again on WireShark. 


![image](https://github.com/user-attachments/assets/1d68183f-c845-49fa-a4b7-19318917c8fa) 


In this part of the lab I filtered traffic to SSH only in WireShark.  In Windows vm I entered SSH command and logged into Linux VM and observed traffic in WireShark. 

