# Active Directory Lab
## Description
### What is Active Directory ? 

Active Directory is a directory service developed by Microsoft for managing and organizing resources within a networked environment. It is commonly used in Windows-based networks to centralize and control network resources, such as user accounts, computers, printers, and security policies.

## Lab Structure

<img src="https://github.com/uzair-khn/Active_Directory/blob/main/p3.PNG" width="1000px" height="350px">

I would like to inform you that our homelab will be undergoing a division into four distinct steps.

## Step-by-Step Guide

### 🌐 Installing & Configuring the virtual environment for both Windows Server 2019 & Windows 10
- Install virtual box and ISOs for given links: 
  - VirtualBox : <a> https://www.virtualbox.org/wiki/Downloads </a>
  - Windows Server 2019 💿 : <a> http://www.microsoft.com/en-us/evalcenter/download-windows-server-2019 </a>
  - Windows 10 💿 : <a> https://www.microsoft.com/en-us/software-download/windows10 </a>
  
- Setting Up the Virtual Environment
  -  This is for Windows Server 2019, all the things by defualt. Just change : <br/>
        Version to : Other Windows 64 bit, <br/>
        Network to : Add another adopter with defualt and change to internal network, & <br/>
        Choose Windows 10 standard (User Desktop Experience) & Custom Setting, when installing it. <br/>
        ***Its time for a coffee break ☕️*** 
        
### ⚙️ Configuring Windows Server 2019
- Open Windows Server 2019, and it seeems to be very complicated but it is not.
  - First, Open the the network connection window, and change the Ethernet names for ease like: <br/>
    Path: Ethernet -> Properties -> Details <br/>
    Ethernet having home ip address like 10.?.?.? or 192.?.?.?     -->  Rename it to "Internet" <br/>
    Ethernet having loop back ip address like 162.?.?.? or 127.?.?.?     -->  Rename it to "Internal" <br/>
    
  - Assign IPs now to the Ethernet:
    For Internal -- <br/> Change IP to **172.16.0.1**, mask to **255.255.255.0** & DNS to **127.0.0.1"** (loopback as this server act as DNS also).
    

  
