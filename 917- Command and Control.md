# COMMAND AND CONTROL (C2) - MITRE ATT&CK  
**Framework: Mythic**


In cybersecurity, **Command and Control (C2 or C&C)** refers to the infrastructure that cybercriminals use to control compromised devices, such as computers or networks, through a central server.  
This server acts as a command hub, allowing attackers to send orders to infected devices and receive information from them.  

## Command and Control Process  

1. **Infection**  
   A device is infected with malware (malicious software).  

2. **Connection**  
   The malware establishes a connection with a Command and Control server, which acts as the attacker's operations center.  

3. **Control**  
   From the C2 server, the attacker can send commands to infected devices to perform various actions, such as:  
   - Stealing information (passwords, files, etc.).  
   - Downloading and installing additional malware.  
   - Launching attacks on other systems.  

4. **Data Collection**  
   Infected devices can send information back to the C2 server, including stolen data, results of executed actions, and more.  
