# Investigate Mythic Agent

**How to identify a C2 attack:**  
It can usually be identified through **network telemetry**. A C2 session will have **high and constant network traffic**.

**Process creation usually linked with network activity:**  
- Example: `RUNDLL32` → Check if there is a **parent process** creating it.  
- Verify if there are **outgoing connections** (PowerShell, etc.) to **public IPs**.


**NOTAS**

<img width="886" height="634" alt="image" src="https://github.com/user-attachments/assets/58d6c252-e766-45ea-b021-c1f17fa70439" />


If we have **Sysmon telemetry**, always check the **Process GUID** for correlation.  
The **Process GUID** will evaluate all events generated from the selected session (e.g., PowerShell).

**Observe:**  
- `event.action`  
- `event.code`  
- Messages: hash  

We will look for **file creation** and verify the **Process GUID**.  
Also check `processId` and `parentProcessId`, and look for any processes related to them.


Try to create new telemetry, but the **EDR detects it as malware** and automatically removes it.

<img width="886" height="511" alt="image" src="https://github.com/user-attachments/assets/e5df7ea8-93ac-40b1-9074-2ca1a5c3e283" />
<img width="886" height="533" alt="image" src="https://github.com/user-attachments/assets/e77014db-f353-4517-80f3-f6e9a2f8861c" />


Go to **Discover** and verify that we have the alert showing that the **Elastic EDR quarantined the file**.

<img width="519" height="606" alt="image" src="https://github.com/user-attachments/assets/c93dbc7e-5aa2-46a9-b8e7-b4f30b959b82" />
<img width="770" height="156" alt="image" src="https://github.com/user-attachments/assets/b0ad9dee-0368-42b3-9ecb-dce56cbf87a1" />
