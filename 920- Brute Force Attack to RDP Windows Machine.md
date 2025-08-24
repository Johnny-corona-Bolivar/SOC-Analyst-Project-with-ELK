# Brute Force Attack on a Windows RDP Machine  

First of all, we will create a file on the Windows server that contains **sensitive information**.

<img width="139" height="78" alt="image" src="https://github.com/user-attachments/assets/eb9ae4bd-5a42-43de-985a-7e4f695990f8" />

## Setting Up Kali Linux for the Attack  

Next, we need to set up **Kali Linux**, which is not in our VPC.  

For this exercise, we will use the most popular wordlist, **rockyou**, but due to the large number of words, we will only use **at least 50 entries**.  
This way, the brute-force attack will be faster.  

> Note: We will edit the wordlist to include the **username and password** of the Windows server.

<img width="644" height="92" alt="image" src="https://github.com/user-attachments/assets/d69c378c-5b5f-4292-ba00-46f06ad4182a" />
<img width="739" height="239" alt="image" src="https://github.com/user-attachments/assets/f2eb8ab7-3eb3-4406-ae40-b87aab1cf79e" />



## We will be using **Crowbar**:  

**Crowbar** is a brute-force tool designed to attack services such as **RDP, SSH, VNC, and OpenVPN** using password lists.  
It is ideal for penetration testing in **controlled environments**.

<img width="666" height="437" alt="image" src="https://github.com/user-attachments/assets/6fd21188-9591-43b2-9932-cffdfa878620" />

Once the tools are set up, we will follow the next steps according to the attack diagram.  

We will use the following **Crowbar** command:  

    ```bash
     crowbar -b rdp -u Administrator -C soc-wordlist.txt -s <public-ip-of-server>/32 -p 3389 -v

This command means:

- We will connect using the RDP protocol.
- The username will be Administrator.
- We will use the wordlist for the brute-force attack.
- The attack will target the server's IP via port 3389.

For this project Crowbar did not work.
<img width="886" height="201" alt="image" src="https://github.com/user-attachments/assets/fc760f35-5e49-4e09-89e8-d2cccc576132" />

## Using Hydra for Brute-Force Attacks  

Alternatively, **Hydra** can be used.  
It is more robust and powerful when performing brute-force attacks compared to other tools.


<img width="886" height="92" alt="image" src="https://github.com/user-attachments/assets/6d55e754-e317-4705-bb0c-cb33949dfc42" />
<img width="886" height="114" alt="image" src="https://github.com/user-attachments/assets/d4c10e1e-0fec-423f-b60f-5f8b9aa34796" />

The attack worked. We used the following options with **Hydra**:  

- `-t 1` : Number of parallel tasks (can be increased).  
- `-v` : Verbose mode.  
- `-f` : Stop the attack once a valid password is found.  
- `-l` : Specify the username.  
- `-P` : Use a wordlist or dictionary.  
- `rdp://<ip>:3389` : Protocol and target IP for the attack.


**At this point, we can connect to the **Windows server via RDP** from our Kali Linux machine.**
<img width="886" height="86" alt="image" src="https://github.com/user-attachments/assets/8adf8805-e9a6-41e4-977d-2fdc421fc049" />
<img width="886" height="400" alt="image" src="https://github.com/user-attachments/assets/c0de681a-0c9e-41d2-9eae-a4bd3aa3a649" />



<img width="628" height="673" alt="image" src="https://github.com/user-attachments/assets/8382ef92-e09c-414f-900c-96dad9c71e24" />
<img width="688" height="597" alt="image" src="https://github.com/user-attachments/assets/0898236f-9af9-4eaa-a2b4-e393aff40e5b" />


Next, we **disable the antivirus** on the Windows server to prevent detection and avoid triggering security alerts.
<img width="663" height="502" alt="image" src="https://github.com/user-attachments/assets/26457591-b244-41f8-bd55-aedda443cf4c" />



## Using Mythic C2  

Now we use the **Mythic C2 framework**.  

We need the agent available on GitHub:  

[https://github.com/MythicAgents/Apollo](https://github.com/MythicAgents/Apollo)

<img width="886" height="116" alt="image" src="https://github.com/user-attachments/assets/4818ce03-7909-4c07-8647-0564a0336cd1" />


**Profile:** [https://github.com/MythicC2Profiles/http](https://github.com/MythicC2Profiles/http)

<img width="886" height="73" alt="image" src="https://github.com/user-attachments/assets/e065c3be-91d5-448a-8db9-899389c5c07e" />
<img width="886" height="116" alt="image" src="https://github.com/user-attachments/assets/d022a582-2cf1-476d-af5a-46d4bd75453b" />
<img width="886" height="119" alt="image" src="https://github.com/user-attachments/assets/01ce4197-b527-40b7-b8f5-c494120acb8a" />

We can create a payload

<img width="886" height="127" alt="image" src="https://github.com/user-attachments/assets/7a395991-ad44-464c-b456-6f987657364f" />
<img width="886" height="470" alt="image" src="https://github.com/user-attachments/assets/deab1dcd-cc56-40e4-9a29-aa0c19288d2a" />


All command included:

<img width="886" height="340" alt="image" src="https://github.com/user-attachments/assets/5bbfe007-2ecf-4b99-bfad-fdd38f141628" />
<img width="886" height="474" alt="image" src="https://github.com/user-attachments/assets/af326ac5-3153-4c3e-acd9-c6900d8f2c8a" />


We made a few changes

<img width="886" height="517" alt="image" src="https://github.com/user-attachments/assets/a20a155f-4320-49c1-b1d8-b4be31869244" />
<img width="774" height="558" alt="image" src="https://github.com/user-attachments/assets/f7ee6e01-1793-48db-a6d4-962bd7118b14" />
<img width="886" height="231" alt="image" src="https://github.com/user-attachments/assets/cef97b92-e12a-4da1-8d0f-e2bb9823647f" />


## Download and Modify the Agent  

We copy the link:  

[https://45.76.254.251:7443/direct/download/c5a6b541-921e-4359-8b7d-7d67691a1ad1](https://45.76.254.251:7443/direct/download/c5a6b541-921e-4359-8b7d-7d67691a1ad1)  

It needs to be **modified** to better conceal it before using it on the target system.

<img width="886" height="370" alt="image" src="https://github.com/user-attachments/assets/98d9a7ca-ed92-4cb2-8d41-30433310a356" />
<img width="750" height="172" alt="image" src="https://github.com/user-attachments/assets/4e7e0d53-e817-4f75-8f51-88d2b976241b" />
<img width="886" height="148" alt="image" src="https://github.com/user-attachments/assets/d1e10e71-7151-4b32-b875-f39477b101a6" />
<img width="759" height="164" alt="image" src="https://github.com/user-attachments/assets/0dacf4a5-3e66-4e3b-91cd-47ca3c31de3b" />



## Execute the Payload from Mythic PowerShell  

Next, using **PowerShell** from Mythic, we execute the payload from the folder where it is located, which is named **one**.

<img width="886" height="173" alt="image" src="https://github.com/user-attachments/assets/a5cc5cc4-1eb9-4907-a273-7ada49b6f527" />

We need to **allow port 9999** on the Mythic server to enable proper communication with the agent.
From the **Kali Linux RDP console**, we execute the payload.  
> Note: The syntax uses **win**, not **min**.

<img width="886" height="181" alt="image" src="https://github.com/user-attachments/assets/528ba66f-e839-49b6-a55e-5c39b575c620" />
<img width="886" height="176" alt="image" src="https://github.com/user-attachments/assets/bb9ac1d3-8fbf-4e22-84c6-c5d3cbecc539" />



## Connection Established  

`200 OK` indicates that we now have a **successful connection** to the target.

<img width="884" height="405" alt="image" src="https://github.com/user-attachments/assets/1154ab5a-20ea-43e2-8e6c-05cb6f07adfb" />
<img width="811" height="192" alt="image" src="https://github.com/user-attachments/assets/e16e46db-9bf5-4726-bc57-9ed6fe0ed962" />


## Run the Payload  

After running the payload, you should see it appear as a **callback** in the Mythic C2 server.

<img width="886" height="119" alt="image" src="https://github.com/user-attachments/assets/f78de46a-378c-4638-a5b5-1977d7c97c4b" />


