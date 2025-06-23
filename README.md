<h1>Integrating Slack within  Splunk to Automate Response Actions</h1>


<h2>Description</h2>
Project consists of integrating Slack with Splunk to generate real-time brute force alerts and notifications. The integration was configured using a generated API token and a YAML file that defined the required scopes for the Splunkbot. A detection alert was created within Splunk, and notifications were delivered to a designated Slack channel when the alert conditions were met. The configuration showcases how Splunk can automate communication and streamline incident awareness through messaging platforms.
<br />


<h2>Languages and Utilities Used</h2>

- <b>Slack</b> 
- <b>SPL</b>
- <b>YAML</b>
- <b>Auth Token Keys</b>

<h2>Environments Used </h2>

- <b>Mac OS</b>


<h2>Program walk-through:</h2>

<p align="center">
From the homescreen, I navigated to "find more apps" at the top left: <br/>
<img src="https://i.imgur.com/4evmnX7.png" height="80%" width="80%" alt="Honeypot Steps"/>
<br />
<br />
Searched for Slack and installed "Slack Notifications Alert":  <br/>
<img src="https://i.imgur.com/KCPMdGp.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Once installed I navigated to api.slack.com to grab my Auth Token key that will be used in configuration, I selected create app, and "from manifest" since I have an account: <br/>
<img src="https://i.imgur.com/5tXfD5S.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Selected my workspace:  <br/>
<img src="https://i.imgur.com/lUjfOrI.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Input YAML code:  <br/>
<img src="https://i.imgur.com/EumU7vw.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Clicked create, you can see the scope for the bot that will be created based on the YAML code:  <br/>
<img src="https://i.imgur.com/wi847zt.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Installing app into Slack workspace:  <br/>
<img src="https://i.imgur.com/aHUfuFp.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Allowing specific permissions:  <br/>
<img src="https://i.imgur.com/7cCNGJX.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Copied API:  <br/>
<img src="https://i.imgur.com/gcmoULp.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Navigated back to Splunks home screen. In the apps section at the top left clicked manage, typed splunk and clicked setup. Once on that screen I pasted my API token:  <br/>
<img src="https://i.imgur.com/QAMXqfd.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Opened my Slack app, found the apps tab and typed splunk in the search bar. I then clicked on the first result:  <br/>
<img src="https://i.imgur.com/ncxalpD.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
The splunkbot was added as seen in the bottom left. I created a new channel and invited the Splunkbot:  <br/>
<img src="https://i.imgur.com/m3s27O8.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
From there I navigated back to Splunk, clicked on settings and clicked users:  <br/>
<img src="https://i.imgur.com/07B9KIM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
I created a new user and assigned their role within Splunk:  <br/>
<img src="https://i.imgur.com/YpPyTIL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Logged out and logged in as the new user:  <br/>
<img src="https://i.imgur.com/CALchUb.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
I then logged out, and intentionally failed logging back in as that user until I became locked out:  <br/>
<img src="https://i.imgur.com/p1X2EPb.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
I logged back in as admin, from there I used SPL to query the failed logins by that user and to display in a table format:  <br/>
<img src="https://i.imgur.com/IX25LSk.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
After viewing the table, I wanted to see the data from the events view. I then queried the following in the search head to create an alert:  <br/>
<img src="https://i.imgur.com/DFMLHqd.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
I gave this rule a title and description, set it in real time since this was a test enviornment(not best practice for production enviornment) and set trigger action to alert in Slack:  <br/>
<img src="https://i.imgur.com/UGf2rFK.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Alert settings:  <br/>
<img src="https://i.imgur.com/4QqLFaI.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Once created, I edited the permissions:  <br/>
<img src="https://i.imgur.com/I3IjL4U.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Navigated back to user settings and unlocked user Kyle's account. Logged out of admin, failed logging in as Kyle again to test the integration of Slack:  <br/>
<img src="https://i.imgur.com/oAjS3Rq.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
The integration was successful, I was notified in Slack via the Splunkbot that user Kyle failed logging in based on the alert I built:  <br/>
<img src="https://i.imgur.com/HEsUw8d.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
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
