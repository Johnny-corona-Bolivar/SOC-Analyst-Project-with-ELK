# Ubuntu Server 24.02 Setup: SSH Server & Viewing Authentication Logs

We need to create the server the same way as before.  

All authentication logs are located in the following directory:  

<img width="886" height="177" alt="image" src="https://github.com/user-attachments/assets/94560500-db12-4e7a-ad43-d870cc4274f5" />

We need to check the **auth.log**,  
which contains all logs related to authentication activities.  

If we leave it running for a while, we will see a lot of **failed authentication attempts**.  

<img width="886" height="175" alt="image" src="https://github.com/user-attachments/assets/1541d769-68ac-4076-a33a-030d9767d5cc" />

<img width="886" height="216" alt="image" src="https://github.com/user-attachments/assets/1d5fe145-1e0c-4f03-874a-5ec1ec78d6f6" />

<img width="886" height="208" alt="image" src="https://github.com/user-attachments/assets/53153cdd-89ce-4e7f-85bf-36ab8113ff9d" />

Now we do it again but with root

<img width="886" height="339" alt="image" src="https://github.com/user-attachments/assets/cc44db3f-5bd5-44c8-aa5b-5822f305d77f" />
<img width="886" height="353" alt="image" src="https://github.com/user-attachments/assets/bc92ac95-a761-47dc-92e9-f422dfcc8d0f" />

We use a **cut** command to visualize and select fields separated by spaces.  

