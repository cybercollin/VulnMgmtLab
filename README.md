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
<h3><i>Discover</i></h3><br/>
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
<h3><i>Prioritize</i></h3><br/>
Upon completion of the scan, we can view the results and sort the data by Severity. The vulnerabilities that lead to database exposure/tampering or critical data leaks are the most important to deal with first:
<br/><br/>
<img src="https://i.imgur.com/TKTHgie.png" height="80%" width="80%" alt="OpenVAS Vulnerability Management Scanning"/>
<br />
<br />
<h3><i>Assess</i></h3><br/>
The main purpose of the Assess step is to establish a working baseline for the issues plaguing the assets of the organization. Consistency in the baseline helps to stay on top of vulnerabilities as the landscape of cybersecurity is forever evolving and the business' needs usually change over time (new technologies/patches open potential doors to new vulnerabilities). <br/><br/>

In the case of this lab, as we saw in the previous image, several of our top severity vulnerabilities frequently involve the PHP server-side scripting language. I filtered the results based on the keyword PHP to see how many total vulnerabilities were involved with this technology. The search resulted in 173 out of the 341 initial results (nearly half of all the problems were based around PHP):
<img src="https://i.imgur.com/LEW600g.png" height="80%" width="80%" alt="OpenVAS Vulnerability Management Scanning"/>
<br />
<br />
<h3><i>Reporting</i></h3>
Documentation and reporting on known vulnerabilities is a critical component of a cybersecurity engineer’s workflow. Keeping a good record of vulnerability scanning ensures effective communication throughout the organization, accountability for due diligence and regulatory compliance.<br/><br/>

OpenVAS offers a comprehensive breakdown for researchers if you click on individual vulnerabilities found during a scan. I chose to investigate the PHP End of Life Detection (Windows) as it presented the highest severity. 
<img src="https://i.imgur.com/lvxM9tq.png" height="80%" width="80%" alt="OpenVAS Vulnerability Management Scanning"/>
<br />
<br />
<img src="https://i.imgur.com/e4mbrZ3.png" height="80%" width="80%" alt="OpenVAS Vulnerability Management Scanning"/>
<br />
<br />
In this case the issue is that the version of PHP used on the Windows machine running XAMPP was deprecated years ago and is unsafe to use due to many known vulnerabilities that were addressed in future versions. The solution is straightforward: <b>Update the PHP version to a version that is still supported.</b>

Vulnerability scanners are valuable tools to expedite vulnerability management processes, however, they are prone to false-positive results, as well. Results of reports should be confirmed by the security engineer before being passed onto the remediation team. Results of issues like default credentials can be easily confirmed by a remote credential login attempt by the engineer to verify the issue is actually a true-positive vulnerability.<br /><br />




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
