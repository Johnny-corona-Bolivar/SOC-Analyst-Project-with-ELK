# RDP Protocol


**RDP (Remote Desktop Protocol)** is a proprietary protocol developed by Microsoft that allows users to connect and control a computer remotely over a network.  
It provides a graphical interface to access the desktop, applications, and files of the remote system as if you were physically in front of it.  


If it is exposed, attackers can perform brute force attacks and, if successful, use lateral movement to gain more access.  

Organizations that have RDP open and exposed must **disable it** or place it **behind a VPN**.  

**Shodan** and **Censys:** We can use these tools to verify which services are exposed to the Internet.  

## Recommendations

- **Turn off or disable RDP**  
- **Enable MFA (Multi-Factor Authentication)**  
- **Restrict access:** Limit by IP range or allow only authorized users  
- **Improve passwords:** Use PAM (Pluggable Authentication Modules)  
- **Do not use default accounts**  
