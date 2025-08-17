# Ingest Sysmon and Windows Defender logs into eleasticsearch

<img width="550" height="440" alt="image" src="https://github.com/user-attachments/assets/16740ba4-e8b6-4ccf-84e6-d24242a7493a" />

Add Integrations

<img width="558" height="341" alt="image" src="https://github.com/user-attachments/assets/92e875ae-6d1f-4192-a2a3-567844c0bab6" />
<img width="558" height="171" alt="image" src="https://github.com/user-attachments/assets/72778726-1a20-49be-a741-e5a737933b66" />
<img width="560" height="300" alt="image" src="https://github.com/user-attachments/assets/a195e740-c458-40c4-ab74-298d64fdcf2f" />

Integration name Win-Sysmon, Description collect Sysmon logs

<img width="679" height="245" alt="image" src="https://github.com/user-attachments/assets/1f697a98-d193-4f56-8d4e-83a1ce7649ef" />

The channel name is located in the Windows Server Event Viewer, so we need to connect via RDP and find it in that location.  

- In **Logs** and **Applications** → **Microsoft** → **Windows**,  
- look for the **Sysmon** folder → **Operational**.


<img width="236" height="55" alt="image" src="https://github.com/user-attachments/assets/5190aa37-4b17-4e9a-8baf-ed57e9a96f17" />

<img width="511" height="144" alt="image" src="https://github.com/user-attachments/assets/ba468593-0eda-49a5-82b0-2190d841c0a0" />


- Right-click on **Operational**.  

<img width="531" height="184" alt="image" src="https://github.com/user-attachments/assets/ce03d89e-d5e8-4e3f-b1d3-91f8926112ea" />


- Select **Properties** →  

<img width="616" height="92" alt="image" src="https://github.com/user-attachments/assets/d348691f-f4b0-416c-9b4c-ed43fb840a6b" />

The channel would be the **Full Name**. Copy and paste it where requested earlier.  

<img width="706" height="195" alt="image" src="https://github.com/user-attachments/assets/9d991e9f-d6e9-49a4-8390-24511ebbd401" />

- Here, select the policy you created; in my case, it is named **Windows-policy**.  
- Click **Save** and **Continue** → **Deploy**, and you're done.

<img width="706" height="153" alt="image" src="https://github.com/user-attachments/assets/213466d7-e019-4a3b-9648-3edf33bd2dc5" />

- The same steps are followed to add **Windows Defender logs**,  
- except that in the Event Viewer, you need to look for the corresponding folder.


<img width="386" height="109" alt="image" src="https://github.com/user-attachments/assets/2adc837b-3aa3-47fc-acce-808d0fe8f545" />

- After that, go to **Elasticsearch** → **Discover**.  


<img width="712" height="264" alt="image" src="https://github.com/user-attachments/assets/2521c16e-9e4f-4133-894b-5b0b5068622c" />
<img width="714" height="398" alt="image" src="https://github.com/user-attachments/assets/a5f8eda3-40b8-4a69-9427-d35bcaaae3bc" />

<img width="647" height="302" alt="image" src="https://github.com/user-attachments/assets/742a5643-4d91-4917-896e-a677eb73644e" />

**If you see this, it is an indicator that the agents do not have connectivity with the Elastic Agent.  
In this case, it did not happen to me because the **ELK server port 9200** was open in the firewall, which can be a starting point for troubleshooting.**
