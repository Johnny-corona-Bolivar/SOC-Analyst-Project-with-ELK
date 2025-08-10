# Windows server creation

### Diagram modification

 - To create the Windows server, since if someone tries to compromise my Windows server, they would not have access to anything else in the entire VPC.
  <img width="634" height="581" alt="image" src="https://github.com/user-attachments/assets/c107187b-6442-4a56-ab97-fabdd98a1158" />



  
### The process of creating the Windows server is the same as the previous server:  
- Deploy → Deploy New Server  
- Choose type: Will be shared CPU  
- Location: the same as the previous one  
- Select the hardware you want with the necessary capacity  
- The software will be Windows (I chose 2022)


<img width="886" height="404" alt="image" src="https://github.com/user-attachments/assets/acea21f5-a502-486e-8636-9344a4c26b79" />

- The only difference from the previous one is that, as specified in the diagram, it will not be inside the VPC, so it is not selected.

   <img width="722" height="380" alt="image" src="https://github.com/user-attachments/assets/3c186078-658a-4f75-b8dc-0a5f4b065162" />
   <img width="886" height="602" alt="image" src="https://github.com/user-attachments/assets/257a94ad-768c-41df-b725-99ce5e015c90" />

And we expose RDP to the internet to later monitor the traffic.


