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
- Open Windows Server 2019, and it seeems to be flow over the brain but it is not, believe me.
  - Open the the network connection window, and change the Ethernet names for ease like: <br/>
    Path: Ethernet -> Properties -> Details <br/>
    Ethernet having home ip address like 10.?.?.? or 192.?.?.?     -->  Rename it to "Internet" <br/>
    Ethernet having loop back ip address like 162.?.?.? or 127.?.?.?     -->  Rename it to "Internal" <br/>
    
    Assign IPs now to the Ethernet:
    For Internal -- <br/> Change IP to **172.16.0.1**, mask to **255.255.255.0** & DNS to **127.0.0.1"** (loopback as this server act as DNS also).
    
    Now change the Server name to your choice but remember it. <br/> Path will be Settings -> About -> Rename this PC
- Now, its time to add services on the Windows Server. 🔥 <br/>
 🎯 **Central/Main Path** --- Server Manager -> Add Roles & Features 
   - ***Adding Active Directory Domain Service*** <br/><br/>
      Choose next until select service : Choose Active Directory Domain Service and then Finish. <br/>
      Wait for few minutes until its done and close the windows. <br/>
      
      You will see a flag with yellow object at top right corner click it & choose Post Deployment Config. <br/>
         Choose the option: <br/> **Add new forest & add domain name you want. <domain_name.com>** <br/> **Write password** & finish it.
         <br/> Machine will restart. Give Password you wrote in domain section.
      
      Now make your own admin account on Domain server you create. <br/> 
      Path --- Start Menu -> AD Users & Computers <br/><br/>
         ➡️🖱️ Domain Name & select New -> Organizational Unit <br/>
                 Name this as ADMINS <br/><br/>
         ➡️🖱️ Domain Name & select New -> Users <br/> 
                 Fill it as you want but uncheck 1 option & check 3 option. <br/><br/>
              ➡️🖱️ Admin Name & select Properties -> Members Of -> Add <br/>
                      Fill the blank portion with: Domain Admins <br/>
      Log out and sign as other user that you created as Domain Admin..... <br/> <br/>
                   
      ***& its done. Heyooo, its complicated right. 🎉 <br/>
              ***Its time for a snack break 🥤🍿*** 


              
      
      
      
      
      
  
