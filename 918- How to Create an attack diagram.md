# How to Create an Attack Diagram  

Create an **attack diagram** that maps out your attack plan.  

An attack diagram visually represents each step of the attack process, including how the attacker gains access, moves within the system, and achieves their objectives. 

## Attack Simulation Diagram  

In the following diagram, we will simulate a **brute-force attack** on a Windows server.  

### Attack Phases  

1. **Phase 1 – Brute Force Attack**  
   - Perform a brute-force attack against the Windows server to obtain valid credentials.  

2. **Phase 2 – RDP Access**  
   - Once authentication is successful, connect via **Remote Desktop Protocol (RDP)**.  
   - Execute basic commands such as:  
     - `whoami`  
     - `net user`  
     - `net group`  
     - `ipconfig`  

3. **Phase 3 – Disable Antivirus**  
   - Disable the antivirus on the Windows server to avoid detection and prevent security alerts.  

4. **Phase 4 – Install Mythic Framework**  
   - While connected through **PowerShell (IEX)**, install the **Mythic C2 framework**.  
   - Connect it to our external server to establish command and control.  

5. **Phase 5 – Execute C2 and Establish Persistence**  
   - Run the **C2 agent** on the server.  
   - Configure persistence to maintain long-term access.  

6. **Phase 6 – Data Exfiltration**  
   - Extract the files created on the server and send them back to the attacker-controlled system.  





<img width="838" height="633" alt="image" src="https://github.com/user-attachments/assets/cc09de10-8b9d-4c7e-805b-367993bb9292" />
<img width="831" height="502" alt="image" src="https://github.com/user-attachments/assets/f9c051ff-7a1d-49d2-bd7d-60d2b911d125" />
<img width="834" height="298" alt="image" src="https://github.com/user-attachments/assets/c4e3c95a-4442-4375-933a-b15fdc49c1dd" />



