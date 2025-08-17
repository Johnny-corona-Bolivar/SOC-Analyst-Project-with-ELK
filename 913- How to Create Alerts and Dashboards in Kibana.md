# Create SSH Brute Force Alert and Dashboard


We look for **failed authentication** in the Kibana dashboard because a brute force attack tries multiple combinations.  

Keywords to use:  
- **failed attempts**  
- **user**  
- **source IP**
- **Country names**

<img width="740" height="378" alt="image" src="https://github.com/user-attachments/assets/639594fd-35de-44ee-82bd-5b8f269dbaa0" />

To view the failed attempts and evaluate them,  
we use the field name filter and obtain these results.  

<img width="600" height="586" alt="image" src="https://github.com/user-attachments/assets/e84de419-ec57-40b4-ab30-95d24fe960c6" />

We need to search for the users who have attempted to log in.  
The **Username** field shows who has tried to do so.  

<img width="583" height="499" alt="image" src="https://github.com/user-attachments/assets/82d8051e-b391-4cf5-ac4c-bbc78854fa87" />

We will also add the **Source IP** and **Source.Geo.Country Name** fields.  
Then, we will filter only the failed attempts to create the alert.  

<img width="886" height="297" alt="image" src="https://github.com/user-attachments/assets/318bcc59-3a12-4797-905a-ba98238a0144" />

To select it, choose **failed** and click the **+** button.  

<img width="539" height="192" alt="image" src="https://github.com/user-attachments/assets/e184644d-737e-47db-8542-acb392cca402" />

<img width="735" height="389" alt="image" src="https://github.com/user-attachments/assets/509f0f40-2868-4ae6-8672-1ef093e04f38" />

Create Alert

<img width="886" height="302" alt="image" src="https://github.com/user-attachments/assets/0ac509ce-bb35-4bd6-9609-227b5411cc58" />

Then create search threshold

<img width="503" height="714" alt="image" src="https://github.com/user-attachments/assets/1fe0d8bb-7c1b-480f-afc4-adce99354d31" />

We can edit the values so that the alert triggers if, for example, it detects **5 failed attempts within 5 minutes**.  
Set the desired values, save, and give it a name: **SSH Brute Force Activity - Jay**.  
After it is created, it will appear in the alerts list.  

<img width="361" height="492" alt="image" src="https://github.com/user-attachments/assets/82f3a4d0-8760-4683-a1f9-974f23850ab8" />

Lets go to maps

<img width="886" height="169" alt="image" src="https://github.com/user-attachments/assets/9f01ac2b-72ce-43ed-84b4-bfd5956df239" />

Then, we paste our query with our filters:  
system.auth.ssh.event:* AND agent.name:Linux-Server-Jay AND system.auth.ssh.event:Failed

<img width="511" height="234" alt="image" src="https://github.com/user-attachments/assets/7e7ca554-f57f-4530-888f-5b29465c3ce2" />
<img width="345" height="291" alt="image" src="https://github.com/user-attachments/assets/7889aef7-9fe2-4c43-8d58-8098ee0e6cd8" />
<img width="636" height="316" alt="image" src="https://github.com/user-attachments/assets/8b2efa84-f743-40f6-860c-c40f8254e1ee" />
<img width="725" height="341" alt="image" src="https://github.com/user-attachments/assets/e01f7dea-7ac4-4a7e-a0ac-dc4c376200f4" />
<img width="734" height="348" alt="image" src="https://github.com/user-attachments/assets/49c529a4-1684-4510-b406-77953d0f80af" />
<img width="886" height="292" alt="image" src="https://github.com/user-attachments/assets/1a583130-025b-4706-b55b-33ecb780fba5" />
