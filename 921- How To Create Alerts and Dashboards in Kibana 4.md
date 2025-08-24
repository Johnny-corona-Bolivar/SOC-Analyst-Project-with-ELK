# How To Create Alerts and Dashboards in Kibana (4/4)

## SIEM Query Example  

    ```text
    Query: svchost-win-jay.exe and event.code: 1 and winlog.event_data.Hashes: *1792731E030B7FE35A7EB21C9F907EAE6E4AC381DE918003F2709185C4CE0A5A*

This query searches for events where:
- The process name is svchost-win-jay.exe
- The event code is 1
- The file hash matches 1792731E030B7FE35A7EB21C9F907EAE6E4AC381DE918003F2709185C4CE0A5A


<img width="886" height="272" alt="image" src="https://github.com/user-attachments/assets/691b1a00-1ce6-4d03-bd92-79595100e4d3" />

Alert when we have a process that is been created


## SIEM Query Example  

    ```text
     svchost and event.code: 1 and (winlog.event_data.Hashes: *1792731E030B7FE35A7EB21C9F907EAE6E4AC381DE918003F2709185C4CE0A5A* 
     or winlog.event_data.OriginalFileName: Apollo.exe)


This query searches for events where:
- The process name is svchost
- The event code is 1
- Either the file hash matches 1792731E030B7FE35A7EB21C9F907EAE6E4AC381DE918003F2709185C4CE0A5A
or the original file name is Apollo.exe

<img width="886" height="398" alt="image" src="https://github.com/user-attachments/assets/b47804c6-650b-41f1-8054-dd7bee71d297" />


## Updated SIEM Query  

We will remove the server name (**svchost**) since we obviously would not know it, and use the following query:  

      ```text
     event.code: 1 and (winlog.event_data.Hashes: *1792731E030B7FE35A7EB21C9F907EAE6E4AC381DE918003F2709185C4CE0A5A* 
     or winlog.event_data.OriginalFileName: Apollo.exe)

This query searches for events where:
- The event code is 1
- Either the file hash matches 1792731E030B7FE35A7EB21C9F907EAE6E4AC381DE918003F2709185C4CE0A5A
or the original file name is Apollo.exe

<img width="886" height="406" alt="image" src="https://github.com/user-attachments/assets/ade7bb18-0cfd-47ed-a16a-8d1c17f0bcc6" />

Let`s create the Rules 
custom rule 
to create the rule QUERY:

- host.hostname
- message
- winlog.event_data.CommandLine
- winlog.event_data.ParentImage
- winlog.event_data.ParentCommandLine
- winlog.event_data.ParentProcessGuid
- winlog.event_data.User
- winlog.event_data.CurrentDirectory
- we can use other queries


<img width="696" height="465" alt="image" src="https://github.com/user-attachments/assets/77d32000-f238-4df9-8687-35928d1f5ecc" />
<img width="699" height="233" alt="image" src="https://github.com/user-attachments/assets/330eedcc-d585-4316-95e4-b7e4fbba8297" />
<img width="699" height="425" alt="image" src="https://github.com/user-attachments/assets/9455a48d-a017-47fc-8771-8ef696e07ead" />
<img width="886" height="360" alt="image" src="https://github.com/user-attachments/assets/dc84be5f-3647-401b-8429-57beb3d5d60d" />
<img width="886" height="183" alt="image" src="https://github.com/user-attachments/assets/91a66a65-710d-45d5-958c-f42301e3b4dd" />


# Rules and Alerts  

## Event ID 1 – Process Creation (powershell, cmd, rundll32)  

**Query:**  

    ```text
     event.code: 1 and (powershell or cmd or rundll32) and event.provider: Microsoft-Windows-Sysmon

Description:
This rule triggers an alert when a new process is created with Event ID 1 in Sysmon, specifically if the process is one of the following:
- powershell
- cmd
- rundll32

It uses the Microsoft-Windows-Sysmon provider.

<img width="886" height="415" alt="image" src="https://github.com/user-attachments/assets/93937331-6e60-4862-9f7d-ea57ed2eedc8" />




## Event ID 3 – Network Connections (External)  

**Query:**  

    ```text
      event.code: 3 and event.provider: Microsoft-Windows-Sysmon and winlog.event_data.Initiated: true

Description:
This rule triggers an alert when any process initiates an outbound network connection with Event ID 3 in Sysmon.
It specifically looks for connections that are initiated (winlog.event_data.Initiated: true) and uses the Microsoft-Windows-Sysmon provider.



<img width="886" height="476" alt="image" src="https://github.com/user-attachments/assets/012154a0-af8b-4d92-8285-9cbfce9e8b3d" />



## Event ID 5001 – Windows Defender  

**Query:**  

       ```text
       event.code: 5001 and event.provider: Microsoft-Windows-Windows Defender

Description:
This rule triggers an alert when Windows Defender generates an event with Event ID 5001.
It uses the Microsoft-Windows-Windows Defender provider.

<img width="886" height="382" alt="image" src="https://github.com/user-attachments/assets/1b5bacbf-1d79-40aa-b936-b3d7d5ed549c" />


# Dashboards  

We will create **3 simple dashboards** that will display important information.  
These dashboards can be further improved over time.

## Event ID:1

<img width="886" height="398" alt="image" src="https://github.com/user-attachments/assets/6cd79be5-fbb4-4b56-8ee0-2731104d7a18" />

## Event ID : 3

<img width="886" height="197" alt="image" src="https://github.com/user-attachments/assets/14db6ebd-f0fe-4574-a407-c091aef8215f" />

## Event ID: 5001

<img width="886" height="387" alt="image" src="https://github.com/user-attachments/assets/1f93d94e-c21e-4048-9ef3-256533fce866" />



