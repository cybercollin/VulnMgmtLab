<h1>Vulnerability Management with OpenVAS</h1>

<h2>Description</h2>
This project demonstrates the execution of a Vulnerability Management lifecycle iteration using the National Institute of Standards and Technology’s Cybersecurity Framework to improve the security posture of a business. A vulnerability scan will be walked-through using the software OpenVAS (preinstalled on a Ubuntu box provided by TryHackMe). The six phases of the Vulnerability Management Lifecycle are: Discover, Prioritize, Assess, Report, Remediate and Verify.
<br />


<h2>Languages and Utilities Used</h2>

- <b>OpenVAS</b> 

<h2>Environments Used </h2>

- <b>Ubuntu 18.04.6</b> 

<h2>Project walk-through:</h2>

<p align="center">
 @@Discover@@
On the Linux box I navigated to the Greenbone Source Edition web application, in this lab environment it was reached through the browser at http://10.10.23.104:9392. Logging in with our sample credentials within this lab brings us to the Web GUI interface: <br/><br/>
<img src="https://i.imgur.com/Ul1sxzR.png" height="80%" width="80%" alt="OpenVAS Vulnerability Management Scanning"/>
<br />
<br />
<img src="https://i.imgur.com/VLOJ5AC.png" height="80%" width="80%" alt="OpenVAS Vulnerability Management Scanning"/>
<br />
<br />
The first step in vulnerability management is to take an inventory of assets (software, hardware, services, configurations etc.) that will be involved during a scan of the systems and networks associated. I added a new Target by hovering over Configuration and clicking Targets: <br/><br/>
<img src="https://i.imgur.com/3Xn6t7a.png" height="80%" width="80%" alt="OpenVAS Vulnerability Management Scanning"/>
<br />
<br />
I added a new target called Windows and entered the local IP address (there is already a virtual instance of Windows on this simulated network available through the lap platform). At this point a security engineer could deploy this across many subnets and systems for a more thorough scan of the organization: <br/><br/>
<img src="https://i.imgur.com/FG5rQ9C.png" height="80%" width="80%" alt="OpenVAS Vulnerability Management Scanning"/>
<br />
<br />
Next, set up a new scanning task. I hovered over Scans and selected Tasks to open the task scheduler. I called the new task Windows-Task and selected the Windows machine we previously configured:  <br/><br/>
<img src="https://i.imgur.com/X4i4Otx.png" height="80%" width="80%" alt="OpenVAS Vulnerability Management Scanning"/>
<br />
<br />
<img src="https://i.imgur.com/VrZRl2v.png" height="80%" width="80%" alt="OpenVAS Vulnerability Management Scanning"/>
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
