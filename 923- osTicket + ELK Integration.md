# osTicket + ELK Integration

**GitHub:** [osTicket API Documentation](https://github.com/osTicket/osTicket/blob/develop/setup/doc/api/tickets.md)

We will start by clicking on the **Admin Panel** in osTicket.


<img width="886" height="321" alt="image" src="https://github.com/user-attachments/assets/474ffb45-294c-4d87-b3d0-403838d7b7f4" />
<img width="588" height="158" alt="image" src="https://github.com/user-attachments/assets/b313baca-3af8-4b24-b0fd-b62d35c3a556" />
<img width="886" height="171" alt="image" src="https://github.com/user-attachments/assets/e3e5eddc-e2c0-411f-8d7f-c2368c97282a" />

Then **API**

<img width="283" height="147" alt="image" src="https://github.com/user-attachments/assets/f6b1e967-9ec6-4efd-bc8d-b0f4d0763630" />

In the case of the IP, since both osTicket and the ELK server are inside the same VPC, I will use the **private IP** of my ELK server.  
If they were not in the same VPC, I would need to use the **public IP** instead.

<img width="875" height="363" alt="image" src="https://github.com/user-attachments/assets/e49ccd22-2d39-45f0-a348-7c5e4f434218" />

Check the option **Can Create Ticket**.  

ELK Server Private IP:  

<img width="679" height="490" alt="image" src="https://github.com/user-attachments/assets/e18b9ad3-72ae-4943-ae8a-76e68cebce83" />

**REMEMBER CHECK THE OPTION: CAN CREATE TICKET**

**And save the KEY**

<img width="886" height="205" alt="image" src="https://github.com/user-attachments/assets/f9b81ec0-723e-4d0f-a538-034a02a3ed5b" />

Next, go to the **ELK server** and navigate to:  

**Stack Management → Connectors → Create Connector**

<img width="370" height="322" alt="image" src="https://github.com/user-attachments/assets/9d0c584f-dbb1-4bd3-bd3c-e50e1c5006dc" />
<img width="546" height="478" alt="image" src="https://github.com/user-attachments/assets/c03dff30-cb57-4ca4-adeb-c4629451ca4b" />
<img width="587" height="442" alt="image" src="https://github.com/user-attachments/assets/dfcf70a0-36f1-44c5-a4e3-69704db9107f" />


**use wEBHOOK**

<img width="674" height="523" alt="image" src="https://github.com/user-attachments/assets/fe5d8ff2-f034-498e-ba65-28ef1b54fdbc" />

The IP used is the **private IP** of the server.  

Click **Save and Test**, and we will use a **payload** from the osTicket GitHub repository.

<img width="691" height="532" alt="image" src="https://github.com/user-attachments/assets/f5b83614-f7e6-456b-83f8-6357569c1b12" />

Go to the **osTicket interface** and click on the **Agent Panel**.

<img width="886" height="63" alt="image" src="https://github.com/user-attachments/assets/a224184e-5c36-4e76-99af-28b434044449" />
<img width="886" height="253" alt="image" src="https://github.com/user-attachments/assets/173b57d1-a492-446b-b568-ffa1764e1b66" />

## Troubleshooting

If the test fails, make sure that the **private IP** is configured in osTicket.  
Otherwise, there may be **network connection issues** when trying to connect via RDP.

<img width="886" height="441" alt="image" src="https://github.com/user-attachments/assets/c3a7da65-1a74-4f42-8377-2df94a349714" />

Make sure it is configured as shown: if the **local IP** of the osTicket server appears instead, it must be configured **manually**.

<img width="772" height="889" alt="image" src="https://github.com/user-attachments/assets/4ad1112d-a308-47a6-9a8a-ebc72ba63524" />


Once everything we have done so far is installed and configured correctly...



