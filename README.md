<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Preparing Active Directory Infrastructure in Azure</h1>
In this project, I create two Virtual Machines, one running Windows Server to represent a Domain Controller. The other Virtual Machine will act as the client that joins the domain. Later on, I'll deploy Active Directory, create users in the domain using a script to log in from as clients, and then manage the accounts, as well as update group policies to practice being in a real IT environment.  <br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Computer)
- Remote Desktop Connection
- Various Command-Line Tools
- Windows Powershell

<h2>Operating Systems Used </h2>

- Windows Server 2022, 2vCPUs, 8GM RAM
- Windows 10 Pro (22H2), 2vCPUs, 8GB RAM

<h2>High-Level Steps</h2>

- Setup Domain Controller in Azure
- Setup Client-1 in Azure


<h2>Deployment and Configuration Steps</h2>


 1.) First, I create a resource group to have our virtual machines in. Then I create a virtual network as well for them.
 
![image](https://github.com/user-attachments/assets/956245bb-e615-4047-9db6-1f0e3743d5ae)

<p>
</p>
<br />

![image](https://github.com/user-attachments/assets/87b17cc2-4dc0-4341-9cf6-d91e72aa2169)

<p>
Once we have our resource group and network created, I'll set up our first virtual machine that will act as our Domain Controller.
</p>
<br />

![image](https://github.com/user-attachments/assets/f1b6cf17-26a9-4d8c-a07c-a68be5d07c7c)


<p>
In the Networking tab of this VM, I'll make sure it will create itself on the virtual network I just created. I'll leave all other settings default and create this VM:
</p>
<br />

![image](https://github.com/user-attachments/assets/a081bbe1-09ad-43b7-b10e-ee572ed8ab71)


<p>
Now, I'll create another VM that will serve as the client. The image for this machine should be Windows 10, NOT Windows Server like I did for the previous machine:
</p>
<br />

![image](https://github.com/user-attachments/assets/44df1df8-704a-4229-a4c6-a3e08c07fb53)


<p>
Now I have to to set up our Domain Controller private IP address to static. This controller will double as a DNS server, which I will tell our client to use as a DNS server later.
</p>
<br />

![image](https://github.com/user-attachments/assets/95ff712c-fca2-452b-bde8-3b2ae15a605c)


<p>
  After going into remote desktop connection and connecting to Domain Controller, I'm going to disable the firewall. You should see everything is checked as disabled.
</p>
<br />

![image](https://github.com/user-attachments/assets/52a5aa33-537b-4a94-9c47-379d8736799f)

<p>
Next, I need configure our clients DNS settings to the DC. To start, back in Azure, I'll grab the DCs private IP address then input DC's private ip in client's DNS settings.
</p>
<br />

![image](https://github.com/user-attachments/assets/587df318-ec4d-4368-98f1-85d071fe229e)


<p>

</p>
<br />













