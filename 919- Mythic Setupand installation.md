# Setup Mythic C2 Server and Learn How Mythic Works  

The server is installed in the same way as before in our Vultr   

Once **Mythic** is installed, we connect via **SSH**, update the repositories, and start preparing the environment.  
Since we need **Docker**, we will proceed with its installation.  

<img width="845" height="100" alt="image" src="https://github.com/user-attachments/assets/86515138-d6fe-4a4b-b9dd-f7819f5f40b0" />
<img width="886" height="285" alt="image" src="https://github.com/user-attachments/assets/61fe8b8c-945b-4143-af1d-8d8d34598cf0" />

### Clone the Mythic Repository  

We will clone the repository to be used from GitHub:  

    ```bash
     git clone https://github.com/its-a-feature/Mythic

<img width="886" height="234" alt="image" src="https://github.com/user-attachments/assets/cbd0c1b2-43d4-4ce6-a777-bb4956176481" />



After cloning the repository, we go to the **Mythic** directory.  
Since we will be using Docker, we need **mythic_docker**.  

     ```bash
     cd Mythic
     ./mythic_docker.sh

<img width="886" height="129" alt="image" src="https://github.com/user-attachments/assets/c9f43c3a-5217-48a0-9dc9-680d2319263e" />
<img width="875" height="78" alt="image" src="https://github.com/user-attachments/assets/47233586-29fa-4d54-8b83-0a4cda5f4f9c" />


Inside the **Mythic** directory, we run the following command to build and set up Mythic with Docker:  

     ```bash
        make

<img width="886" height="408" alt="image" src="https://github.com/user-attachments/assets/d9a62bb9-c4c7-4f10-be6e-8187fdce4a1c" />
<img width="698" height="53" alt="image" src="https://github.com/user-attachments/assets/14aa9954-8e07-4527-8ba3-ab2dab79d917" />
<img width="886" height="410" alt="image" src="https://github.com/user-attachments/assets/78eb1e06-b283-4bff-b387-75c3ed5eb6fb" />

At this point, you can already **log in** to the Mythic C2 server.  
Access the web interface using the server’s IP address and the configured credentials.

Remember to allow the 7443 port

<img width="886" height="518" alt="image" src="https://github.com/user-attachments/assets/b29d1e8a-4deb-4942-8640-0aff7283212b" />

The password is located in the **.env** archive of Mythic.  
It is a hidden file, so you need to use the following command to list it:  

        ```bash
           ls -la

<img width="813" height="67" alt="image" src="https://github.com/user-attachments/assets/2273be60-2d04-4c60-9957-a888e7980af3" />
<img width="886" height="407" alt="image" src="https://github.com/user-attachments/assets/cd5214b9-71e8-4247-9995-7567f2586842" />

## OPTIONAL

Now, we create a **firewall** to allow incoming connections only from specific servers, instead of allowing access from the entire internet.  

This helps secure the Mythic C2 server by restricting unauthorized access.

<img width="886" height="317" alt="image" src="https://github.com/user-attachments/assets/8d697ba9-a208-42a6-8775-11d6b33c266d" />

Next, we add the **Mythic server** to the firewall rules.  
This ensures that only the Mythic server and authorized hosts can access the environment


<img width="886" height="448" alt="image" src="https://github.com/user-attachments/assets/8c80133d-ec62-44a3-8eb9-3727fb36f596" />

