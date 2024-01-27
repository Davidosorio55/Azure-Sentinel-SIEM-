<h1>Azure Sentinel (SIEM)</h1>

<h2>Description</h2>
For this project, I established Azure Sentinel (SIEM) and connected it to a vulnerable live virtual machine called a honey pot. Through this setup, I monitored real-time attacks, specifically RDP Brute Force attempts from all around the world. I also employed a custom PowerShell script to retrieve the geolocation details of attackers, which were then used to visualize on the Azure Sentinel Map.
<br />


<h2>Languages and Utilities Used</h2>

- <b>PowerShell</b> 
- <b>Microsoft Azure</b>

<h2>Environments Used </h2>

- <b>Windows 10</b> 

<h2>Walk-through:</h2>

<p align="center">
Creation of a virtual machine: <br/>
<img src="https://i.imgur.com/CpDfUBy.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Creation of log analytics workspace:  <br/>
<img src="https://i.imgur.com/lmi6tYY.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Log analytics configuration (Defender Plans):  <br/>
<img src="https://i.imgur.com/9gmFNRi.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Log analytics configuration (Data Collection):  <br/>
<img src="https://i.imgur.com/2KcTPiZ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Add the workspace to sentinel:  <br/>
<img src="https://i.imgur.com/CYeY73V.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Start the virtual machine:  <br/>
<img src="https://i.imgur.com/ECqaNID.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Copy the public ip address:  <br/>
<img src="https://i.imgur.com/2kVHqp2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Connect to it using RDP ( Remote Desktop Protocol):  <br/>
<img src="https://i.imgur.com/vCJpIAl.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Open security logs in the virtual machine using eventviewer:  <br/>
<img src="https://i.imgur.com/w8xqNNe.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Ping The VM without disabling the firewall:  <br/>
<img src="https://i.imgur.com/KkIuSnQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Disable the firewall in The VM:  <br/>
<img src="https://i.imgur.com/G5ReXd4.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
New ping command now with the firewall disabled:  <br/>
<img src="https://i.imgur.com/xUT2MMZ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Create an account in ipgeolocationapi and copy the API KEY:  <br/>
<img src="https://i.imgur.com/W9Kx0vm.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Download an powershell script from github:  <br/>
<img src="https://i.imgur.com/RZG2LW2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Open the script with powershell ISE and change the api key to your personal key from ipgeolocation:  <br/>
<img src="https://i.imgur.com/g1EAlzW.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Start the script:  <br/>
<img src="https://i.imgur.com/qa7adJO.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Go to ProgramData in the vm using WindowsKeybind+R and copy the failed_rdp log file:  <br/>
<img src="https://i.imgur.com/D2cvHYD.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Save the file copied from the vm and then create a custom log with that file:  <br/>
<img src="https://i.imgur.com/6RF7doo.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Costum log (Settings Record Delimiter):  <br/>
<img src="https://i.imgur.com/rUoE483.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Costum log (Settings Colletion Path):  <br/>
<img src="https://i.imgur.com/8gpELuh.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Costum log (Details):  <br/>
<img src="https://i.imgur.com/XBEA0NE.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Run the costum Log:  <br/>
<img src="https://i.imgur.com/GR7FbwR.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Run the following query to extract all the fields:  <br/>
<img src="https://i.imgur.com/jOvHJ35.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Go to workbooks and remove them:  <br/>
<img src="https://i.imgur.com/ZpwSE3h.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Add a new workbook:  <br/>
<img src="https://i.imgur.com/ETHUOX2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Paste the same query as before in the new workbook:  <br/>
<img src="https://i.imgur.com/W6UQCZr.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Create a map and apply the following settings:  <br/>
<img src="https://i.imgur.com/tEfAx5x.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/ivXMmqW.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Heatmap result of our honeypot:  <br/>
<img src=https://i.imgur.com/nRxVPjW.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />



<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
