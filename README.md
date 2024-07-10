# MicroSoft Azure Sentinel SIEM & HoneyPot


<h2>Description</h2>
Updated virson of how to setup Microsoft Azure Sentinel (SIEM) and connect it to a live virtual machine acting as a honey pot. We will observe live attacks (RDP Brute Force) from all around the world. We will use a custom PowerShell script to look up the attackers Geolocation information and plot it on the Azure Sentinel Map.
<br />


<h2>Languages and Utilities Used</h2>

- <b>PowerShell</b> 
- <b>Kusto Query Language (KQL)</b>

<h2>Environments Used </h2>

- <b>Microsoft Azure Sentinel (SIEM)</b>
- <b>Azure Virtual Machines</b>
- <b>Remote Desktop Protocol (RDP)</b>
- <b>Network Security Groups</b>

<h2>walk-through:</h2>

<p align="center">
Sign up free account: <br/>
<img src="https://imgur.com/M8SSQW0.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
VM setup: <br/>
<img src="https://imgur.com/VftOvbl.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />               
Go to advanced settings: <br/>
<img src="https://imgur.com/AQBmugv.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Delete existing rules create a new one & be sure to put * for destination port ranges or the VM wont open with RDP: <br/>
<img src="https://imgur.com/voawl5t.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />  
Create VM: <br/>
<img src="https://imgur.com/WzojZeg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />  
Create a log analytics workspace: <br/>
<img src="https://imgur.com/H87ROTF.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />  
Go to environment settings in Microsoft Defender For Cloud Check What I Have Marked: <br/>
<img src="https://imgur.com/brIY8k5.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />  
All events in data collection: <br/>
<img src="https://imgur.com/tSJrhWl.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />  
Connect to VM: <br/>
<img src="https://imgur.com/1dHAoOh.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />  
Use the Public IP address to login into the VM using RDP: <br/>
<img src="https://imgur.com/qd4oFQm.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />  
Turn off FW for domain,private, and public: <br/>
<img src="https://imgur.com/fKaNj36.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />  
Go to PowerShell ISE and open script but dont run: <br/>
<img src="https://imgur.com/FfFgkoa.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />  
Go to this site and sign up for free and get 1k APIs: <br/>
<img src="https://imgur.com/YrwhTBi.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />  
Paste your API key into this script: <br/>
<img src="https://imgur.com/DZYNej0.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />  
Run Script it might take 10-15 minutes before anything happens: <br/>
<img src=https://imgur.com/uS0L8tf.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />  
All logs will be set to the hidden folder c:\programdata\: <br/>
<img src="https://imgur.com/dIDBzX9.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />  
Create a custom Log in Log Analytics workspace: <br/>
<img src="https://imgur.com/jvVx7T1.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />  
Search for your logs: <br/>
<img src="https://imgur.com/v2X1USG.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />  
Upload some of your logs into the log sample: <br/>
<img src="https://imgur.com/KjEOKap.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />  
Should look like this: <br/>
<img src="https://imgur.com/EtbFASU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />  
Find this hidden folder by searching c:\programData\ in VM and copy the path: <br/>
<img src="https://imgur.com/duAjM1k.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />  
Make sure its the same path or the custom log will not work: <br/>
<img src="https://imgur.com/tYKDnye.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />  
Create log name: <br/>
<img src="https://imgur.com/NWl2tef.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />  
Wait 20 min or so until it shows up in log analytics: <br/>
<img src="https://imgur.com/D1XekQA.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />  
Use this script in a new workbook to organize the geo locations. Make sure your in Log Analytics not in the VM group!: <br/>
<img src="https://imgur.com/4RqY1eW.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />  
Looks like this: <br/>
<img src="https://imgur.com/cyjESto.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />  
Edit the workbook to your liking and just save: <br/>
<img src="https://imgur.com/GYQk4Xl.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />  
You will only get failed RDP loggins when the script is running: <br/>
<img src="https://imgur.com/FfFgkoa.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<p/>
  
  
  
  
  <!--
  
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
