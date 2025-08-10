# VPC Creation

For this project i will use a Vultr as cloud provider

- 1 : Product
  
  <img width="151" height="429" alt="image" src="https://github.com/user-attachments/assets/7c04c113-e09a-4516-8b74-ff7cd264a1c7" />

Select **Network** → then **VPC 2.0** → **Network Location** and choose the country.  
Keep in mind that every time a VPC is created, it must be in the same country or location so they can be visible to each other.


- Ip configuration :
 
  <img width="501" height="301" alt="image" src="https://github.com/user-attachments/assets/c9671fb7-e632-4730-969d-89d5db526c5f" />

- Name it with a personal identifier and click **Add Network** to create the VPC.

  <img width="886" height="153" alt="image" src="https://github.com/user-attachments/assets/38ea279f-8eca-45eb-9105-fa6f66421965" />

## Now we will need to create the virtual machines.  

 Click **Deploy**:

  <img width="602" height="208" alt="image" src="https://github.com/user-attachments/assets/377db268-91ca-4919-a510-cde54e09e46d" />
  <img width="300" height="92" alt="image" src="https://github.com/user-attachments/assets/423cba8c-0a78-4843-acb1-ec2f541dbeb3" />

- Choose default dedicated CPU
  
  <img width="536" height="379" alt="image" src="https://github.com/user-attachments/assets/61ea8dd8-54cb-4bfe-8a6a-0f52abf650d6" />

- Choose the same location :

  <img width="357" height="401" alt="image" src="https://github.com/user-attachments/assets/248dbd37-2bef-45cb-9f81-8e8c164e3272" />

- size
    
  <img width="886" height="349" alt="image" src="https://github.com/user-attachments/assets/38c504a7-1484-4fc7-9cf1-2c32f54137b0" />

### For elasticsearch i choose Ubuntu

  <img width="547" height="509" alt="image" src="https://github.com/user-attachments/assets/fade2922-0d4b-46eb-beaa-322025b70310" />
  
- We disabled el automatic backups And we activated the VPC network

  <img width="714" height="663" alt="image" src="https://github.com/user-attachments/assets/f115a226-3b6f-47ae-8ea4-ff5a5e44dc62" />
  <img width="525" height="286" alt="image" src="https://github.com/user-attachments/assets/ca695aed-5ae6-453f-b32c-f13bddf6a8fa" />

 - We must ensure that the VPC is the same one created previously; if the IP is not displayed, later when configuring the server, we can obtain it using the interface.

   <img width="886" height="125" alt="image" src="https://github.com/user-attachments/assets/758dce6d-2c88-4512-87ca-7b2925b90c22" />
   <img width="758" height="367" alt="image" src="https://github.com/user-attachments/assets/f9cedf31-a3db-4288-aa7e-70e1506bd907" />

 -  It will provide us with a public IP and credentials to connect via SSH. When connected, we will configure the server by installing the necessary resources. We will connect via PowerShell via SSH

    <img width="778" height="169" alt="image" src="https://github.com/user-attachments/assets/ff72d533-ba02-44ab-98b1-b0392e17562d" />

- Apt-get update && apt-get upgrade -y

   <img width="886" height="457" alt="image" src="https://github.com/user-attachments/assets/5a1a8d5a-f5f5-4232-b50c-efb59be24bec" />

- After updating, we verify the IP, which is 172.31.0.3, located within the specified range. Now we will download Elasticsearch by searching for it on the internet.


   <img width="542" height="644" alt="image" src="https://github.com/user-attachments/assets/7c2911ab-383f-42a8-b818-3fa6de9fb3e3" />

 - As you can see, we choose the version. Right-click the button and copy the download link, then go to the server.

    <img width="886" height="50" alt="image" src="https://github.com/user-attachments/assets/3e34cd1d-44a1-4982-8b54-57794fb81e78" />
    <img width="886" height="144" alt="image" src="https://github.com/user-attachments/assets/d094ff50-d370-4882-a81f-15a93641f5b5" />
    <img width="855" height="94" alt="image" src="https://github.com/user-attachments/assets/bfd6608a-c019-4457-9234-68d4e8928cdd" />

**Note:**  
 Keep in mind the auto-configuration section, as it provides the username and password for Elastic.  
 If you don't copy it, you will need to reset the password using the command:  

`Reset the password of the elastic built-in superuser with '/usr/share/elasticsearch/bin/elasticsearch-reset-password -u elastic'.`

- We open the `.yml` file with nano.

  <img width="886" height="124" alt="image" src="https://github.com/user-attachments/assets/c5d8af66-2b04-4846-92be-4e479f1e3e05" />

- Open `elasticsearch` with nano and edit the following options since we want Elasticsearch to run in our created environment and not on localhost.

  <img width="580" height="273" alt="image" src="https://github.com/user-attachments/assets/3b7de8ed-c618-45c8-aaeb-4b1dd85b898e" />

- Now, what is needed is that only we have access, not any external computer, so we will configure a firewall.

   <img width="147" height="111" alt="image" src="https://github.com/user-attachments/assets/6d407320-cc9d-4840-b8e4-2011d1a13a55" />
   <img width="218" height="407" alt="image" src="https://github.com/user-attachments/assets/670c8a7f-dbda-497d-b507-b70777a08135" />
   <img width="600" height="210" alt="image" src="https://github.com/user-attachments/assets/63c28bd7-5cf0-4e38-b8a4-e01e9c58d87a" />
   <img width="621" height="241" alt="image" src="https://github.com/user-attachments/assets/950dfdfc-9258-47c6-8ca9-946a1999c2c5" />

        Select **Custom**.  Enter the range of our IPs, and that's it.  Now, update in PowerShell.

   <img width="886" height="308" alt="image" src="https://github.com/user-attachments/assets/81edf3ff-10ea-413e-b742-0fe2a63c7dc2" />



### KIBANA

  <img width="570" height="280" alt="image" src="https://github.com/user-attachments/assets/2cb03604-1e93-422f-99da-8bb8bb3d4581" />

 - Select the OS, right-click the button, and copy the download link.
 - We would use the same steps as before.

   <img width="886" height="53" alt="image" src="https://github.com/user-attachments/assets/08fe33e3-5ab8-4067-9ffa-d18bdc3d1f3d" />
   <img width="886" height="60" alt="image" src="https://github.com/user-attachments/assets/3ded8660-38ef-4bd6-9cc4-c3c268e35b8a" />
   <img width="886" height="121" alt="image" src="https://github.com/user-attachments/assets/8d29f723-7487-4007-86a7-12a8401b7657" />
   <img width="716" height="109" alt="image" src="https://github.com/user-attachments/assets/99a28bd6-85f3-4cf6-86e1-f670b0a35c31" />

- We will update the `kibana.yml` configuration file.

   <img width="706" height="102" alt="image" src="https://github.com/user-attachments/assets/5998cf5b-eb1b-486d-8cdb-c1358003cc81" />
   <img width="703" height="238" alt="image" src="https://github.com/user-attachments/assets/368a5b96-d117-40ab-a537-77b95362ffda" />

- Updated
  
    <img width="534" height="214" alt="image" src="https://github.com/user-attachments/assets/07937537-3353-4c69-a722-c7b6eaca8142" />
    <img width="802" height="244" alt="image" src="https://github.com/user-attachments/assets/09cb711e-1716-49ca-ab9a-9edd3598a2eb" />
    <img width="886" height="398" alt="image" src="https://github.com/user-attachments/assets/9f0463fe-ed20-4290-a4b3-9ea5ea761eaf" />

- The only thing left is to generate the Kibana enrollment token.  
  Go to the directory `cd /usr/share/elasticsearch/bin`, where all the binaries are located, and focus on: `elasticsearch-create-enrollment-token`.

    <img width="886" height="179" alt="image" src="https://github.com/user-attachments/assets/d59ece33-717c-4202-8d74-31ad66eb6f4f" />

- Run `./elasticsearch-create-enrollment-token –scope kibana` and copy the provided token.  
- Now, open Kibana in the browser at:  
   `http://155.138.221.119:5601/`

- In case an error like this occurs:

   <img width="475" height="409" alt="image" src="https://github.com/user-attachments/assets/9149a647-2008-4b47-9e66-5a1de95a92c5" />

   - Check if the services are running.

   <img width="544" height="280" alt="image" src="https://github.com/user-attachments/assets/64d5bbe5-d3bc-4e04-8308-7f7f7067ad39" />

   - You should verify the firewall rules, and if everything is fine, the next step is to allow port 5601 through the SSH console using: 
       `ufw allow 5601`

   <img width="495" height="119" alt="image" src="https://github.com/user-attachments/assets/6d95626f-e80c-4772-9e3c-8fbe684498ba" />


- Now it will ask us for the token that was created.

    <img width="475" height="326" alt="image" src="https://github.com/user-attachments/assets/a840574a-d39d-4035-8ec7-94f1583ab650" />
    <img width="501" height="318" alt="image" src="https://github.com/user-attachments/assets/02259f37-7735-4d4c-a58b-f4b0b95ce338" />

- `cd /usr/share/kibana/bin` — go to the binaries, run `ls`, and look for the file named `kibana-verification-code`.

   <img width="886" height="65" alt="image" src="https://github.com/user-attachments/assets/128efae5-5074-47db-be26-df8f5a37d812" />
   <img width="886" height="111" alt="image" src="https://github.com/user-attachments/assets/2d16a5bb-9334-4f66-95bb-87e1113c9a67" />
   <img width="557" height="324" alt="image" src="https://github.com/user-attachments/assets/421e2c06-dde7-439b-9688-b476dc724c77" />
   <img width="568" height="447" alt="image" src="https://github.com/user-attachments/assets/0d3e8079-2366-4508-b63a-fe3c6827c72e" />



- It will ask us to log in with the credentials created earlier during the Elasticsearch installation.  
  It may require an API Integration Key:  We need to generate it.

   <img width="886" height="341" alt="image" src="https://github.com/user-attachments/assets/5a62e8c3-f14c-4080-ad90-558023c3686e" />
   <img width="886" height="121" alt="image" src="https://github.com/user-attachments/assets/9c47b1a6-d0ea-4586-9cae-e059563340ae" />
   
- Now, we add them to the keystore.

   <img width="886" height="25" alt="image" src="https://github.com/user-attachments/assets/ddc25436-8618-4860-8085-864ddee164b8" />
   <img width="886" height="29" alt="image" src="https://github.com/user-attachments/assets/c09137f2-537a-4710-8ce9-cc2fb73ec277" />

     - This step will be repeated for the other two keys.













   







  
    




  




  

