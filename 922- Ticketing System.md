# What is a Ticketing System?  

A **ticketing system** is software that allows you to **manage, process, and track requests, incidents, or inquiries** from clients or users.

# Installation and Setup of OsTicket


We will create a **Windows server** to install OsTicket.  
Once the OsTicket server is created, we will connect via **RDP** to start the installation of the system.  
We will install **XAMPP** to use it as a web server, making it the host for the ticketing system.
We will use the **latest version** of OsTicket, of course.

<img width="886" height="499" alt="image" src="https://github.com/user-attachments/assets/522ca545-6668-488b-b332-1ac0ddf9d0e8" />
<img width="553" height="488" alt="image" src="https://github.com/user-attachments/assets/f942dd9d-70c6-4965-9e09-dddc085da584" />
<img width="778" height="549" alt="image" src="https://github.com/user-attachments/assets/04337397-cd61-445b-a396-0571b53f00f9" />

Next, we will configure **XAMPP** to allow and authorize our OsTicket server's IP.
Next, we will go to the **Apache admin** option.

<img width="667" height="113" alt="image" src="https://github.com/user-attachments/assets/62384133-2636-48bf-9304-bd52dab5c554" />
<img width="438" height="109" alt="image" src="https://github.com/user-attachments/assets/ce91362d-d97e-4210-b4d8-fa11fcff391f" />
<img width="238" height="113" alt="image" src="https://github.com/user-attachments/assets/5ea7e3f9-4846-4edf-b3e8-6ddd2b10dbcf" />
<img width="886" height="248" alt="image" src="https://github.com/user-attachments/assets/79bdb09f-3db2-43da-b865-479cf5737519" />


We will use the **root** of localhost and then click on **Login Information**.

<img width="886" height="249" alt="image" src="https://github.com/user-attachments/assets/008be80a-c884-4570-87cf-ceecb3f51ffa" />
<img width="866" height="531" alt="image" src="https://github.com/user-attachments/assets/7e976b64-80a1-43eb-8654-3ea3c4da49bc" />


We will change some values:  
- The **hostname** will be updated as specified.  
- The **password** will be changed to `Winter2024`.


<img width="803" height="213" alt="image" src="https://github.com/user-attachments/assets/057f0377-534f-42ec-be5f-1d7297d5fb90" />

Update phpMyAdmin (PMA)  
We will also update **phpMyAdmin (PMA)** to ensure it is using the latest version and security settings.
The password will remain the same: `Winter2024`.

<img width="849" height="109" alt="image" src="https://github.com/user-attachments/assets/4c91c63c-d3d8-47c5-99a9-21398b6a92a8" />
<img width="886" height="344" alt="image" src="https://github.com/user-attachments/assets/db6772dc-acd0-4b44-b905-6cd053819725" />


## Edit Configuration Files  
Next, we will **edit the configuration files** to set up and customize the system.

<img width="616" height="408" alt="image" src="https://github.com/user-attachments/assets/d95d6bdc-e2ce-4407-a91d-142b6ef51d43" />

## Edit Properties  
Next, we go to **Properties** and make the necessary edits.

<img width="653" height="227" alt="image" src="https://github.com/user-attachments/assets/83522722-34e4-4bae-9e4a-bc0e10d9229b" />

Original File

<img width="401" height="484" alt="image" src="https://github.com/user-attachments/assets/6f6bc335-258e-44f0-b15b-f80a4b5be067" />


We will edit the **domain** and set it to the **public IP of the OsTicket server**.

<img width="716" height="158" alt="image" src="https://github.com/user-attachments/assets/00142fe3-d919-451b-9dc1-a374bf57ec9c" />



## Edit phpMyAdmin Configuration File  

Next, we will **edit the phpMyAdmin configuration file** to apply the necessary settings.

<img width="461" height="211" alt="image" src="https://github.com/user-attachments/assets/c8ce704a-6ac7-4224-9bf4-60b5f806731c" />

**Configure config.inc.php**
We will configure the **config.inc.php** file.  
> Note: It is recommended to **make a backup of the file** before making any changes.

<img width="481" height="150" alt="image" src="https://github.com/user-attachments/assets/240e1572-bf4d-4029-b39b-07cdd9c7bf64" />
<img width="797" height="504" alt="image" src="https://github.com/user-attachments/assets/c3c05b15-ffd6-459e-87f9-c1ca37c05958" />

Edit config.inc.php  
We will edit the file to **set the IP** and the **password** that we changed previously.

<img width="808" height="347" alt="image" src="https://github.com/user-attachments/assets/c2baf5fd-3291-46d3-8ea4-1dc1a3970165" />

PMA

<img width="803" height="139" alt="image" src="https://github.com/user-attachments/assets/cdd70cad-5af8-458f-98ac-de69ba4f05f5" />


**Access from SOC Analyst Laptop**

To access the server from the **SOC analyst's laptop**, we can create a **firewall rule** to allow connections only to the specific ports we want, such as **80** and **443**.

<img width="802" height="233" alt="image" src="https://github.com/user-attachments/assets/f78fce62-04ec-4a9f-93ef-539e40e9742c" />

Inbound rules

<img width="302" height="167" alt="image" src="https://github.com/user-attachments/assets/00026265-3c53-41ef-8d02-50d0ab834f64" />

<img width="391" height="120" alt="image" src="https://github.com/user-attachments/assets/391be49a-1fe6-43ec-b951-d546f6800507" />

<img width="788" height="114" alt="image" src="https://github.com/user-attachments/assets/243fae4b-131e-4ed8-b629-e9b22ef07b76" />

<img width="669" height="400" alt="image" src="https://github.com/user-attachments/assets/8e86af6c-603f-4d70-af60-e2b3ce692f44" />

<img width="886" height="35" alt="image" src="https://github.com/user-attachments/assets/e9c15cee-10fa-403d-ab36-9d1b721b463a" />


# Installation and Configuration of OsTicket  

Next, we proceed with the **installation and configuration** of OsTicket.

we go to: osticket.com

<img width="886" height="304" alt="image" src="https://github.com/user-attachments/assets/c4ec2898-9140-40ae-bbde-a44035f86422" />

<img width="227" height="153" alt="image" src="https://github.com/user-attachments/assets/dcae10df-c803-45b7-9378-1d78a10e851b" />

<img width="367" height="810" alt="image" src="https://github.com/user-attachments/assets/7885314a-27a7-4b05-8252-e0e3e9660779" />
<img width="886" height="219" alt="image" src="https://github.com/user-attachments/assets/d0844f42-ea0e-4da9-8a21-98cef0c588cb" />
<img width="886" height="311" alt="image" src="https://github.com/user-attachments/assets/295a1d9c-30b7-4ede-8513-1c78d070c4a0" />


Then, click **Next** repeatedly until the installation is complete.  
The system will finish downloading and setting up automatically.


<img width="164" height="113" alt="image" src="https://github.com/user-attachments/assets/e0326c8b-ef0f-4eb4-8071-b478f6cd17d7" />


## Extract Files  

The downloaded package will be **extracted** to prepare for installation.

<img width="466" height="256" alt="image" src="https://github.com/user-attachments/assets/95a4fee0-bc5b-4b37-92d2-cc609136465c" />

**extracted again**

<img width="466" height="256" alt="image" src="https://github.com/user-attachments/assets/ac61c6ac-2c16-4862-8bb2-da5fd0c5ceef" />


## Create OsTicket Directory  

We go to the **XAMPP folder** and locate the **htdocs** directory, where the default web content is stored.  
We will create a **new folder named `osticket`** inside it.



<img width="438" height="153" alt="image" src="https://github.com/user-attachments/assets/27fdcec5-e588-4b52-ad8d-04621f3017c5" />
<img width="317" height="413" alt="image" src="https://github.com/user-attachments/assets/e584074f-2e92-4d21-b20d-c7d14c57cb1a" />

Copy Extracted Files  
We will take the files that were **extracted** and place them into the new `osticket` folder

<img width="533" height="205" alt="image" src="https://github.com/user-attachments/assets/eee30928-cf84-43d2-bbd7-b33633064650" />

We will **paste the extracted files** into the folder we created inside **htdocs**.  
Next, we navigate to the address in a web browser to access the OsTicket interface.

<img width="886" height="644" alt="image" src="https://github.com/user-attachments/assets/4be5091f-314c-4b11-a2c2-24af77771050" />
<img width="864" height="592" alt="image" src="https://github.com/user-attachments/assets/a02ea8b2-1520-42b2-aba7-b4cef310e32b" />

We would need to make some configurations.  
Let's go to the file located inside `upload` → then `include`.


<img width="751" height="671" alt="image" src="https://github.com/user-attachments/assets/3a0dc11b-b58a-424d-8c95-b074f0ede5cc" />

Rename:

<img width="238" height="67" alt="image" src="https://github.com/user-attachments/assets/d8401b9a-ad26-4a43-85b8-d001b7206cd5" />
<img width="760" height="953" alt="image" src="https://github.com/user-attachments/assets/ec77e899-d36f-4b2f-be7e-010fdacefbd4" />

And we would already have the basic installation.  
Before filling out the form, it's recommended to create a database first — let's get to it.


<img width="739" height="573" alt="image" src="https://github.com/user-attachments/assets/fa43dc7a-27db-41f9-9251-6e78d1ed9558" />
<img width="298" height="309" alt="image" src="https://github.com/user-attachments/assets/a65619ae-cf2b-48d5-977f-9dbf8cf46d6d" />

All set — now let's go to the home page: <img width="102" height="58" alt="image" src="https://github.com/user-attachments/assets/6660e91f-9a38-4397-964d-8b6b0078d960" />


User accounts — we will grant root privilege permissions using the public IP address of our server.

<img width="850" height="175" alt="image" src="https://github.com/user-attachments/assets/0cd04deb-e012-4559-8bf9-3115b37679bf" />

Database:
<img width="244" height="116" alt="image" src="https://github.com/user-attachments/assets/64bc4c12-9641-4013-a3b6-dd64867d7e08" />



And we grant permissions.

<img width="660" height="750" alt="image" src="https://github.com/user-attachments/assets/747c5344-e982-42fd-9955-08f6ce2238fc" />
<img width="684" height="201" alt="image" src="https://github.com/user-attachments/assets/45967261-bce3-4e1d-bf5d-143e40010013" />

Now we proceed with the installation by filling in the required information.

<img width="746" height="758" alt="image" src="https://github.com/user-attachments/assets/2006e00b-663b-45ad-b13b-e1166f80d4c4" />
<img width="737" height="535" alt="image" src="https://github.com/user-attachments/assets/610d7634-4aea-4ffb-8c95-7f55eaff2ce6" />
<img width="770" height="608" alt="image" src="https://github.com/user-attachments/assets/f784159e-40c8-4b89-9269-7390c7bd464c" />

We're done — we now have the ticketing system set up.

Next, we'll configure the permissions file using PowerShell as administrator.

1. Navigate to the folder where the configuration files are located in XAMPP.
2. Copy and execute the `icacls` command to set the appropriate permissions.

<img width="886" height="240" alt="image" src="https://github.com/user-attachments/assets/8e315009-3bfc-4b76-83b9-f1ea7d27c285" />
<img width="886" height="262" alt="image" src="https://github.com/user-attachments/assets/983cef88-3e90-4f8e-befd-0fd6ec88421d" />



We'll use the staff account and log in with the credentials we previously created — from our host machine, not from the RDP server.

The other link is for the employees, so to speak.

<img width="886" height="296" alt="image" src="https://github.com/user-attachments/assets/3c2756e5-b314-4dc6-9f05-de40515fd856" />
















