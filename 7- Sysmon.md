
# Sysmon (System Monitor)

Sysmon (System Monitor) is a free Microsoft Sysinternals tool that installs as a system service and driver to log detailed events in Windows, especially useful for detection, forensic analysis, and security monitoring.  

When properly configured, it extends the information that the Windows Event Viewer captures by default, allowing a SOC or cybersecurity analyst to gain deep visibility into what happens on an endpoint.  


## What Does Sysmon Do?

Once installed and configured with an XML rules file, Sysmon logs the following activities into the Event Viewer (channel: `Microsoft-Windows-Sysmon/Operational`):

1. **Process creation** (including command line, hashes, process ID, user).  
2. **Network connections** (source/destination IPs, ports, associated processes).  
3. **File creation changes** (including timestamp modifications).  
4. **Driver and DLL loading.**  
5. **File hashing** for malware detection.  
6. **Registry modifications detection.**  
7. **System object access events** (e.g., pipes, etc.).


 <img width="886" height="696" alt="image" src="https://github.com/user-attachments/assets/2d8d40e4-cd2b-49a5-8649-fb5cc41a56f6" />
 <img width="886" height="859" alt="image" src="https://github.com/user-attachments/assets/44e75b57-7f18-4103-a6dc-670f22f68b02" />
 <img width="886" height="797" alt="image" src="https://github.com/user-attachments/assets/539248ab-26b7-4dc4-9090-889aea40b5b0" />



