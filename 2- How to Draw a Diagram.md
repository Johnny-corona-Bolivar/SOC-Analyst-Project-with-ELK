# Diagram

 **Diagram:** for this project we are going to use a  VPC in order to able to guide through the process.
*VPC (Virtual Private Cloud)* allows the creation of a virtual private network with resources such as servers, networks, and storage, all virtualized within the cloud.

  
  ### 1:  
  this is the diagram that we are going to use in order to have a visualization on what we will  create ( project or the network ).
  we can see that the VPC  have an ip range 172.31.0.0-172.31.1.254/24 with the submask ,  inside the VPC we have our ELK server,  ticket server, the windows server , the fleet server and ubuntu server, all of then connected to  ISP, but inside they are
  all connected to the ELK server ,   outside the VPC we have our laptop soc analyst , our c2 command and also the attacker laptop connected to ISP

  
   <img width="671" height="634" alt="image" src="https://github.com/user-attachments/assets/be848aa8-03c0-4574-a7a4-0edabeabb563" />

   

### 2: **follow the project to see where we change the diagram**
this is the same diagram suffered changed , we leaved the windows server with rdp enabled and the ubuntu sever with ssh enabled out of the VPC, in order to provent if someone access to the server the rest to the network is safe.

   <img width="634" height="581" alt="image" src="https://github.com/user-attachments/assets/03de27ee-8499-4628-991a-e62c93d6e2bb" />


  
