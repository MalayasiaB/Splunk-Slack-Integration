<h1>Integrating Slack within Splunk to Automate Response Actions</h1>


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
<img src="./images/filename1.png" height="80%" width="80%" alt="Slack"/>
<br />
<br />
Searched for Slack and installed "Slack Notifications Alert":  <br/>
<img src="./images/filename2.png" height="80%" width="80%" alt="Slack"/>
<br />
<br />
Once installed I navigated to api.slack.com to grab my Auth Token key that will be used in configuration, I selected create app, and "from manifest" since I have an account: <br/>
<img src="./images/filename3.png" height="80%" width="80%" alt="Slack"/>
<br />
<br />
Selected my workspace:  <br/>
<img src="./images/filename4.png" height="80%" width="80%" alt="Slack"/>
<br />
<br />
Input YAML code:  <br/>
<img src="images/filename5.png" height="80%" width="80%" alt="Slack"/>
<br />
<br />
Clicked create, you can see the scope for the bot that will be created based on the YAML code:  <br/>
<img src="./images/filename6.png" height="80%" width="80%" alt="Slack"/>
<br />
<br />
Installing app into Slack workspace:  <br/>
<img src="./images/filename7.png" height="80%" width="80%" alt="Slack"/>
<br />
<br />
Allowing specific permissions:  <br/>
<img src="./images/filename8.png" height="80%" width="80%" alt="Slack"/>
<br />
<br />
Copied API:  <br/>
<img src="./images/filename9.png" height="80%" width="80%" alt="Slack"/>
<br />
<br />
Navigated back to Splunks home screen. In the apps section at the top left clicked manage, typed Splunk and clicked setup. Once on that screen I pasted my API token:  <br/>
<img src="./images/filename10.png" height="80%" width="80%" alt="Slack"/>
<br />
<br />
Opened my Slack app, found the "apps" tab and typed Splunk in the search bar. I then clicked on the first result:  <br/>
<img src="./images/filename11.png" height="80%" width="80%" alt="Slack"/>
<br />
<br />
The Splunkbot was added as seen in the bottom left. I created a new channel and invited the Splunkbot:  <br/>
<img src="./images/filename12.png" height="80%" width="80%" alt="Slack"/>
<br />
<br />
From there I navigated back to Splunk, clicked on settings and clicked users:  <br/>
<img src="./images/filename13.png" height="80%" width="80%" alt="Slack"/>
<br />
<br />
I created a new user and assigned their role within Splunk:  <br/>
<img src="./images/filename14.png" height="80%" width="80%" alt="Slack"/>
<br />
<br />
Logged out and logged in as the new user. I then logged out again, and intentionally failed logging back in as that user until I became locked out  <br/>
<img src="./images/filename15.png" height="80%" width="80%" alt="Slack"/>
<br />
<br />
I logged back in as admin, from there I used SPL to query the failed logins by that user and to display in a table format:  <br/>
<img src="./images/filename16.png" height="80%" width="80%" alt="Slack"/>
<br />
<br />
I used the following query to create an alert:  <br/>
<img src="./images/filename17.png" height="80%" width="80%" alt="Slack"/>
<br />
<br />
I gave the alert a title and description, set it in real time since this was a test enviornment(not best practice for production enviornment) and set trigger action to alert in Slack:  <br/>
<img src="./images/filename18.png" height="80%" width="80%" alt="Slack"/>
<br />
<br />
Alert settings:  <br/>
<img src="./images/filename19.png" height="80%" width="80%" alt="Slack"/>
<br />
<br />
After creation, I edited the permissions:  <br/>
<img src="./images/filename20.png" height="80%" width="80%" alt="Slack"/>
<br />
<br />
Navigated back to user settings and unlocked user Kyle's account. Logged out of admin, failed logging in as Kyle again to test the integration of Slack:  <br/>
<img src="./images/filename21.png" height="80%" width="80%" alt="Slack"/>
<br />
<br />
The integration was successful, I was notified in Slack via the Splunkbot that user Kyle failed logging in based on the alert I built:  <br/>
<img src="./images/filename22.png" height="80%" width="80%" alt="Slack"/>
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
