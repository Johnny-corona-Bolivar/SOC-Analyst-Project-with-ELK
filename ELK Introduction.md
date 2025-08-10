# Introdution to ELK

As we mentioned before, I will use ELK for this project. Let’s start with a brief summary of what ELK is.

**ELK** is an acronym that refers to a set of three open-source tools that work together to collect, process, search, analyze, and visualize data—especially system logs and events.  

---

📦 **ELK Stack** stands for these following tools.

1. **E – Elasticsearch**  : Its a search and data analytics engine that Indexes and allows for fast searching of large volumes of information.  
   - Example: finding all failed login attempts among millions of records.  

2. **L – Logstash**  : Its a tool for processing and transforming data before sending it to Elasticsearch and  Can receive data from different sources (servers, networks, applications) and normalize it.  
   - Example: converting a plain-text log into a structured JSON format.  

3. **K – Kibana**  Its a visualization platform that Allows the creation of dashboards, charts, and alerts with the data stored in Elasticsearch.  
   - Example: displaying in a chart the number of connections from suspicious IP addresses.  

---

🔍 **Purpose of the ELK Stack**  
It is used to centralize logs and analyze them in real time. It is widely used for application monitoring, error detection, and also in cybersecurity as a base for SIEM solutions (for example, Wazuh uses ELK to display security data).  

---

🛠 **Workflow of ELK**:  
1. Logstash receives logs from a firewall and transforms them into a common format follow its  
2. Sends them to Elasticsearch, which indexes them for fast searching and lastly  
3. Kibana displays on a dashboard how many brute-force attacks were detected today.

 **visualization**

   <img width="399" height="260" alt="image" src="https://github.com/user-attachments/assets/943be2f6-c24a-464a-aa60-d1dc38af5c94" />


