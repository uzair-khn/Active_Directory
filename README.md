# Active Directory Lab
## Description
### What is Active Directory ? 

Active Directory is a directory service developed by Microsoft for managing and organizing resources within a networked environment. It is commonly used in Windows-based networks to centralize and control network resources, such as user accounts, computers, printers, and security policies.

## Lab Structure

<img src="https://github.com/uzair-khn/Active_Directory/blob/main/p3.PNG" width="1000px" height="350px">

## Step-by-Step Guide

- Install virtual box and ISOs for given links: 
  - VirtualBox : <a> https://www.virtualbox.org/wiki/Downloads </a>
  - Windows Server 2019 💿 : <a> http://www.microsoft.com/en-us/evalcenter/download-windows-server-2019 </a>
  - Windows 10 💿 : <a> https://www.microsoft.com/en-us/software-download/windows10 </a>
  
### 🌐 Installing & Configuring the virtual environment for Windows Server 2019 
***
- Setting Up the Virtual Environment
  -  This is for Windows Server 2019, all the things by defualt. Just change : <br/>
        Version to : Other Windows 64 bit, <br/>
        Network to : Add another adopter with defualt and change to internal network, & <br/>
        Choose Windows 10 standard (User Desktop Experience) & Custom Setting, when installing it. <br/>
        ***Its time for a coffee break ☕️*** 
        
### ⚙️ Configuring Windows Server 2019
***
- Open Windows Server 2019, and it seeems to be flow over the brain but it is not, believe me. <br/>
  - Open the the network connection window, and change the Ethernet names for ease like: <br/>
    Path: Ethernet -> Properties -> Details <br/>
    Ethernet having home ip address like 10.?.?.? or 192.?.?.?     -->  Rename it to "Internet" <br/>
    Ethernet having loop back ip address like 162.?.?.? or 127.?.?.?     -->  Rename it to "Internal" <br/>
    
    Assign IPs now to the Ethernet:
    For Internal -- <br/> Change IP to **172.16.0.1**, mask to **255.255.255.0** & DNS to **127.0.0.1"** (loopback as this server act as DNS also).
    
    Now change the Server name to your choice but remember it. <br/> Path will be Settings -> About -> Rename this PC
- Now, its time to add services on the Windows Server. 🔥 <br/><br/>
 🎯 **Central/Main Path** --- Server Manager -> Add Roles & Features <br/>
   - ### ***Adding Active Directory Domain Service*** <br/> 
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

   - ### ***Adding NAT to connect to Internet*** <br/>
      Choose next until select service : Choose Remote Access -> Next -> Routing and then Finish. <br/>
      Wait for few minutes until its done and close the windows. <br/>
      
      You will see Tools option at top right corner, click Routing & Remote Access. <br/>
      ➡️🖱️ Domain (local) & select Configure & Enable Routing <br/>
            Choose NAT option -> then, choose public interface option and Finish.
            <br/>Green color appears.
            
   - ### ***Adding DHCP Service*** <br/>
     Choose next until select service : Choose DHCP Server then Finish. <br/>
     Wait for few minutes until its done and close the windows. <br/>

     You will see Tools option at top right corner, click DHCP . <br/>
     Drop down your domain name, then IPv4<br/>
     ➡️🖱️ IPv4 & select New Scope <br/>
     -------- Now, fill name and fill up fields: <br/>
     -------------- Start IP : 172.16.0.100 <br/>
     -------------- End IP   : 172.16.0.200 <br/>
     -------------- Length   : 24 <br/>
     -------------- Mask     : 255.255.255.0 <br/>
     -------------- Go until when add router IP : 172.16.0.1 (our DNS IP) and ADD <br/>
     -------------- Finish & Refresh <br/><br/>
     <Extra : Click to Local Server Configuration -> IE Enhance Security Configuration to OFF> <br/>
  
- Furthermore, we should add some users. <br/><br/>
     Path --- Windows Start -> Active Directory -> Add Users & Computers <br/>
          --- ➡️🖱️ Domain Name & select New -> Organizational Unit <br/>
                 Name this as USERS <br/><br/>
          --- ➡️🖱️ USERS & select New -> Users <br/> 
                 Fill it as you want but uncheck 1 option & check 3 option. <br/><br/>
      
                             & its done. Heyooo, its complicated right.🎉
                                    Its time for a snack break 🥤🍿 
      
      
### 🌐 Installing & Configuring the virtual environment for Windows 10
***
- Setting Up the Virtual Environment
  -  This is for Windows 10, all the things by defualt. Just change : <br/>
        Version to : Windows 64-bit, <br/>
        Network to : Change to internal network (to get IP from DHCP), & <br/>
        Choose Windows 10 PRO & Custom Setting, when installing it. <br/>
        ***Its time for a coffee break ☕️*** 
  
### ⚙️ Configuring Windows Server 2019
***
- Check for these things in Client PC:-
    - ipconfig (should be in scope)
    - try to ping
  
- Connect the Client PC to the Domain you created
  <br/>Path:- System -> About -> Rename this PC (Advanced) -> Change <br/> 
  - Name the PC, <br/>
  - Check the option with domain and write tour domain such as mydomain.com <br/>
  - Username & Password you created in the domain server <br/>
  - Finish <br/>
  
                                  ********* TO CONFIRM, GO TO DOMAIN SERVER & CHECK ADDRESS LEASES ********
  
- Login as other user with username and password and it will be done. 
  
  
  
## THE END

