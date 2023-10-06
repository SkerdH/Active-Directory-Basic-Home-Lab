<h1>Active Directory Home Lab</h1>

<h2>Description</h2>
Create a basic home running lab with active directory. This projects shows how I created an internal server using Active Directory. You can experiment with Group Policies and security settings in a lab, understanding how they impact user and computer configurations. This knowledge is essential for maintaining secure and efficient network environments. An AD lab is an ideal place to practice scripting and automation using PowerShell. Employers often seek IT professionals who can automate repetitive tasks and streamline AD management. You can learn how to manage user accounts, permissions, and access controls effectively. This knowledge is essential for maintaining the integrity and security of an organization's data.
Project endgoal as visual guide:  <br/>
<img src="https://i.imgur.com/w3WotSm.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />


<h2>Languages and Utilities Used</h2>

- <b>ORACLE VM</b>
- <b>Server 2019</b>
- <b>PowerShell</b>
<h2>Environments Used </h2>

- <b>ORACLE VM</b>
- <b>WINDOWS 10</b> 

<h2>Program walk-through:</h2>

<p align="center">
Install Oracle box, Windows Server 2019, and Windows 10. Configure VM using Windows Server 2019 <br/>
<img src="https://i.imgur.com/qMLInPN.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
After Windows finishes instalation on the VM, create a administrator account.  <br/>
<img src="https://i.imgur.com/sMzTtGJ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Once the VM is open click network, followed by ethernet, adapter options, then rename both networks found to simplify future assignments  <br/>
<img src="https://i.imgur.com/9V5PmAN.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Change the ip adress of the internal network<br/>
<img src="https://i.imgur.com/nP8AURB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Use the adress 172.160.0.1 as the ip adress and since it will use itself as a dns use 127.0.0.1 meaning the computer will ping itself  <br/>
<img src="https://i.imgur.com/iHGCvtv.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Download Active Directory Domain Services using Server Manager  <br/>
<img src="https://i.imgur.com/4CsrbhU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Next promote current computer to a domain by clicking on the post deployment configuration. Add a new forest name it mydomain then click until installation is finished. <br/>
<img src="https://i.imgur.com/PcBWxTp.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
If done correctly mydomain should now appear before the account user name in login screen <br/>
<img src="https://i.imgur.com/3X2A5t6.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Once logged back in open Active Directory Users and Computers. Click on mydomain, new, organizational unit then name it _admin. then<br/>
<img src="https://i.imgur.com/0pCqI5R.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
After right click admin,create new user, name it anything, then right click the user click properties, then select membor of and change it to domains admins. Following that
  log out then change user, and loging as what username you selected previously, and the password.<br/>
<img src="https://i.imgur.com/G5Z4kmx.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Next using Server Manager install remote accesss. Following that click tools-routing and remote access. Click the name of you computer then install NAT. Next using
  Server Manager install DHCP server.<br/>
<img src="https://i.imgur.com/MNDSTa3.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
After installation click tools, DHCP, click on the network, then right click set scope on IPV4. Following completion of all options click the server then click authorize, then refresh IPV4<br/>
<img src="https://i.imgur.com/3oNHmtj.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Close everything, and open powershell ise as administrator input the script included in repository inside:  <br/>
<img src="https://i.imgur.com/JljfjMr.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Run following commands to create the list of users, then click play to run the powershell script :  <br/>
<img src="https://i.imgur.com/AX7lW7j.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Create new VM with same settings as before however instead of chosing server 2019 use Windows 10 iso: Finish setup and installation <br/>
<img src="https://i.imgur.com/uEJYToz.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
You can now connect to the internal network and if succesfull it ipconfig should look similar to this. This shows an internal network has been
  created and clients or employees can now succesfully connect to the internet:  <br/>
<img src="https://i.imgur.com/7cfHtUy.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />

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
