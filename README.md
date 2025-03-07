<h1>Basic Home Lab Running Active Directory with Oracle VirtualBox</h1>

 ### [YouTube Demonstration by Josh Madakor that I followed](https://youtu.be/MHsI8hJmggI?si=0qlnNvR4fhvXY6UE)

<h2>Description</h2>
Project consists of running two different virtual machines on Oracle Virtual Box. One virtual machine will be running Windows Server 2019 and serve as a domain controller to house Active Directory. This machine will have two network adapters; one will be used to connect to the outside internet and the other used to connect client machines to the private network that we've created. IP addressing for the internal network will be assigned, the server will be named, Active Directory will be installed and a domain created. The domain will be configured and routed so that clinets on the private network can reach the internet through the domain controller. DHCP will be setup on the domain controller so that when we create our windows 10 machine an ip address will automatically be assigned. Before creating the client virtual machine we will also run a powershell script that will automatically create a thousand users for or Active Directory client base. The second virtual machine, Client1, will have Windows 10 installed and will be connected to the private virtual box network at which point we will log into one of our domain accounts and conclude the lab.<br />


<h2>Languages and Utilities Used</h2>

- <b>PowerShell</b> 
- <b>Active Directory</b>

<h2>Environments Used </h2>

- <b>Windows 10, Windows Server 2019</b> (21H2)

<h2>Program walk-through:</h2>

<p align="center">
Diagram: <br/>
<img width="1359" alt="Image" src="https://github.com/user-attachments/assets/ee94a788-2d53-417e-b482-d2fb44a50861" />
<br />
<br />
Assigning IP address to internal NIC card, loopback address for DNS server:  <br/>
<img width="1327" alt="Image" src="https://github.com/user-attachments/assets/8a9236bc-cb2c-4fbd-9293-0e8864220868" /><br />
<br />
Adding myself as a user/administrator. RAS/NAT allows client to be on private virtual network but still able to access the internet through the Domain Controller: <br/>
<img width="1326" alt="Image" src="https://github.com/user-attachments/assets/5ac6324a-e20b-4856-9627-d23124cfb0e1" /><br />
 <img width="1342" alt="Image" src="https://github.com/user-attachments/assets/c8f5fd24-ee0a-4ea5-84c1-c4fd4aa4a85a" /><br />
DHCP scope applied, DNS is setup:  <br/>
<img src="[https://imgur.com/a/pic4-6JVEnWR" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Create client computer and join to the domain. PowerShell script will be used to create users in Active Directory. Powershell script for user generation from a text file of randomly generated names:  <br/>
<img src="https://imgur.com/a/pic5-7OhjTW9" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Users generated from name script:  <br/>
<img src="https://imgur.com/a/pic7-I1GJMeh" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Create Windows 10 client machine on VirtualBox and run ipconfig and ping in command prompt:  <br/>
<img src="https://imgur.com/a/pic8-J3Sy7cF" height="80%" width="80%" alt="Disk Sanitization Steps"/>
  <img src="https://imgur.com/a/pic3-6gNYucP" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Lease provided to client computer:  <br/>
<img src="https://imgur.com/a/pic10-Qsjugc3" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Confirmation the client computer has been added to the domain:  <br/>
<img src="https://imgur.com/a/pic11-uckKfhZ" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
