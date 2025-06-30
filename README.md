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
<img src="https://github.com/user-attachments/assets/153c453e-836c-4554-9abb-3a82cbf5df1f" height="80%" width="80%" alt="Honeypot Steps"/>
<br />
<br />
Searched for Slack and installed "Slack Notifications Alert":  <br/>
<img src="https://github.com/user-attachments/assets/5d22ed23-496d-4eb1-94e6-ce8a66b6d5c8" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Once installed I navigated to api.slack.com to grab my Auth Token key that will be used in configuration, I selected create app, and "from manifest" since I have an account: <br/>
<img src="https://github.com/user-attachments/assets/669f13f4-f110-442b-8e32-2b61c4e022f2" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Selected my workspace:  <br/>
<img src="https://github.com/user-attachments/assets/33100174-b95b-439a-85d5-f8e1aa6e4b41" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Input YAML code:  <br/>
<img src="https://github.com/user-attachments/assets/592b8aab-727c-4cfe-9cfc-42e52f3642fd" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Clicked create, you can see the scope for the bot that will be created based on the YAML code:  <br/>
<img src="https://github.com/user-attachments/assets/ada4da9e-1047-4b42-8808-e2357519f0b8" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Installing app into Slack workspace:  <br/>
<img src="https://github.com/user-attachments/assets/6472ab57-3b85-4376-a1f0-0c2a9e58ae8d" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Allowing specific permissions:  <br/>
<img src="https://github.com/user-attachments/assets/d8aa1221-799f-4319-80f4-15fbc206fae6" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Copied API:  <br/>
<img src="https://github.com/user-attachments/assets/7024e713-913b-43ea-9c7e-48ec941a4a3d" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Navigated back to Splunks home screen. In the apps section at the top left clicked manage, typed Splunk and clicked setup. Once on that screen I pasted my API token:  <br/>
<img src="https://github.com/user-attachments/assets/494c068c-06d0-4217-810b-7a26522c0e11" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Opened my Slack app, found the "apps" tab and typed Splunk in the search bar. I then clicked on the first result:  <br/>
<img src="https://github.com/user-attachments/assets/8c4bb35a-9a07-4623-824b-c9e3d8cf803d" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
The Splunkbot was added as seen in the bottom left. I created a new channel and invited the Splunkbot:  <br/>
<img src="https://github.com/user-attachments/assets/c3b7a69d-4043-4609-adef-3c321fd3f3fd" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
From there I navigated back to Splunk, clicked on settings and clicked users:  <br/>
<img src="https://github.com/user-attachments/assets/078a72f3-c398-47c6-9071-b2c8ef93c0a2" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
I created a new user and assigned their role within Splunk:  <br/>
<img src="https://github.com/user-attachments/assets/7017d7da-88b4-4d8e-8d9b-26b797eb0bdb" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Logged out and logged in as the new user. I then logged out again, and intentionally failed logging back in as that user until I became locked out  <br/>
<img src="https://github.com/user-attachments/assets/3c98773f-3213-4231-a822-6588d22e9994" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
I logged back in as admin, from there I used SPL to query the failed logins by that user and to display in a table format:  <br/>
<img src="https://github.com/user-attachments/assets/a2b6c09f-aef5-46f3-be3c-c7bfabeea9c3" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
I used the following query to create an alert:  <br/>
<img src="https://github.com/user-attachments/assets/286e2b46-1423-4ffd-8538-b246278bda4a" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
I gave the alert a title and description, set it in real time since this was a test enviornment(not best practice for production enviornment) and set trigger action to alert in Slack:  <br/>
<img src="https://github.com/user-attachments/assets/7eb8682f-d3c9-4a9c-a63b-2f5c30adde21" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Alert settings:  <br/>
<img src="https://github.com/user-attachments/assets/f7f0bc1e-e05c-481d-abdc-82c4929879e1" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
After creation, I edited the permissions:  <br/>
<img src="https://github.com/user-attachments/assets/6eecff39-e3fd-4a11-801a-84f27d8846e0" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Navigated back to user settings and unlocked user Kyle's account. Logged out of admin, failed logging in as Kyle again to test the integration of Slack:  <br/>
<img src="https://github.com/user-attachments/assets/9fe357a0-3126-4d10-980f-58eac2010949" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
The integration was successful, I was notified in Slack via the Splunkbot that user Kyle failed logging in based on the alert I built:  <br/>
<img src="https://github.com/user-attachments/assets/e0f8c8eb-56be-48da-acb5-b4603bd3884e" height="80%" width="80%" alt="Disk Sanitization Steps"/>
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
