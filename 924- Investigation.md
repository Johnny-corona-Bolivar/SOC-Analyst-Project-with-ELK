# How to Investigate an SSH and RDP Brute Force Attack

For an SSH attack, take into account:

- Is this **IP** known for performing brute force activity?  
- Are **any other users** affected by this IP?  
- Were any of the attempts **successful**?  
- If so, what activity occurred after the successful login?  
  (Look for persistence, shell commands, downloaded files, executed programs, etc.)

Use **online tools**: AbuseIP, VirusTotal, etc. Also verify **DNS, websites, source code**, etc.

**Keep in mind:**  
Custom variables in Elastic you would use: `{{context.alerts.0.<variable_name>}}`  
So for IP and username it would be: `{{context.alerts.0.source.ip}}`, `{{context.alerts.0.user.name}}`

<img width="886" height="362" alt="image" src="https://github.com/user-attachments/assets/07da52ec-2498-420c-825f-2730a9467d8c" />
<img width="828" height="426" alt="image" src="https://github.com/user-attachments/assets/44ee6d01-8a93-4465-90c7-0fa168386c06" />
<img width="759" height="517" alt="image" src="https://github.com/user-attachments/assets/0977427a-b88a-465e-ae6d-1e13b50f405f" />
<img width="776" height="409" alt="image" src="https://github.com/user-attachments/assets/084f2009-fadb-4526-b7ec-d36303b31c28" />


Now, let's send it to our **ticket system**.

<img width="886" height="379" alt="image" src="https://github.com/user-attachments/assets/9c360570-51b8-4388-b6e4-691e57136481" />
<img width="886" height="103" alt="image" src="https://github.com/user-attachments/assets/f0b9da81-49a8-4780-9d15-f55c3b67ad90" />
<img width="703" height="191" alt="image" src="https://github.com/user-attachments/assets/86e5800d-4140-4431-b5b2-dff967e7643e" />


<img width="222" height="155" alt="image" src="https://github.com/user-attachments/assets/ee447991-9559-45f3-a008-8528403a9b16" />


<img width="886" height="239" alt="image" src="https://github.com/user-attachments/assets/bfa756cf-1e62-433b-a45e-13daaf5e7c6c" />

**Webhook**

<img width="627" height="367" alt="image" src="https://github.com/user-attachments/assets/debfe20b-a6ee-4b20-b556-e2fba3b9b147" />

We should already have our **osTicket** selected.  

We will use the **same payload**.

<img width="886" height="316" alt="image" src="https://github.com/user-attachments/assets/403ed952-266a-473c-ae0c-ae4d214b0c29" />

Once completed, it should appear in **osTicket**, and it will only be a matter of **closing it** or **continuing the evaluation**.


# How to Investigate an RDP Brute Force Attack

- Is this **IP** known for performing brute force activity?  
- Are **any other users** affected by this IP?  
- Were any of the attempts **successful**?  
- If so, what activity occurred after the successful login?  
  (Look for persistence, shell commands, downloaded files, executed programs, etc.)

**If the answer to question 4 is YES:**  
- Take note of the **time and date** when it occurred, including the **time zone**.  
- Record what happened after the successful login (the alert message may provide a clue).  
- Potential **end time**: time, date, and time zone.

<img width="886" height="362" alt="image" src="https://github.com/user-attachments/assets/29d70f51-d4e3-4bc8-b992-1db559e2c40d" />

