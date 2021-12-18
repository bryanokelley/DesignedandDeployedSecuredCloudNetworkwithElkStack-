Automated ELK Stack Deployment
The files in this repository were used to configure the network depicted below.
![](https://github.com/bryanokelley/DesignedandDeployedSecuredCloudNetworkwithElkStack-/blob/main/Images/Red_Team_Network_%20Diagram.png)
These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the playbook file may be used to install only certain pieces of it, such as Filebeat.
The following are the Ansible Playbooks created and used on the DVWA and Elk Stack:
•	docker-python.yml
•	install-elk.yml
•	filebeat-playbook.yml
•	metricbeat-playbook.yml
This document contains the following details:
•	Description of the Topology
•	Access Policies
•	ELK Configuration
•	Beats in Use
•	Machines Being Monitored
•	How to Use the Ansible Build
Description of the Topology
The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.
Load Balancing
Load balancing ensures that the application will be highly available, in addition to restricting access to the network.
A Load Balancer is designed to ensure that the environment remains available by distributing incoming data to the web servers.
Jump Box
The Jump Box allows for easier administration of the systems within the network by being utilized as a Secure Administrator Workstation. The Jump Box must be accessed prior to accessing any of the webservers (Implementing secure administrative hosts 2021).
Elk Server
Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the logs and system traffic.
Filebeat
Filebeat contains modules that provide observability and secure data sources to monitor the collection, parsing, and visualization of common log formats and translate them to a single command. Automatic default paths are set up based on the operating system, Elasticsearch Ingest Node pipeline definitions, and the Kibana dashboard (Filebeat: Lightweight Log Analysis &amp; Elasticsearch 2021).
Metricbeat
Metricbeat modules collect data from services such as Apache, Jolokia, NGINX, Prometheus, MySQL, and others. These modules can be deployed using docker in a separate container and, once installed, reads information from cgroups and the proc file system without requiring privileged access. Metricbeat is also part of the Elastic Stack and can be shipped to Elasticsearch, Logstash, or Kibana (Metricbeat: Lightweight Shipper for Metrics 2021).
Configuration Details
The configuration details of each machine may be found below:
Name	Function	IP Address	Operating System
Jump-Box-Provisioner	Gateway	10.0.0.4	Linux
Web-1	Webserver-Docker-DVWA	10.0.0.9	Linux
Web-2	Webserver-Docker-DVWA	10.0.0.7	Linux
Web-3	Webserver-Docker-DVWA	10.0.0.10	Linux
Red-Team-Elk	Elk Stack	10.1.0.4	Linux

Access Policies
The machines on the internal network are not exposed to the public Internet.
Only the Jump Box Provisioner machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
•	Personal Public IP Address, not listed for security purposes.
Machines within the network can only be accessed by SSH.
•	The Red-Team-Elk server is accessible using SSH from Jump-Box-Provisioner and web access from the Personal Public IP Address.
A summary of the access policies in place can be found in the table below:
Name	Publicly Accessible	Allowed IP Address
Jump-Box-Provisioner	No	Personal Public IP Address
Web-1	Through Load Balancer	Load Balancer Public IP: 20.127.9.229 & Jump Box: 10.0.0.9
Web-2	Through Load Balancer	Load Balancer Public IP: 20.127.9.229 & Jump Box: 10.0.0.7
Web-3	Through Load Balancer	Load Balancer Public IP: 20.127.9.229 & Jump Box: 10.0.0.10
Red-Team-Elk	No	Personal Public IP Address:5601 & Jump Box: 10.1.0.4

Elk Configuration
Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
•	Automating the installation process allows for deployment to multiple servers simultaneously quickly without physically touching the servers.
The playbook implements the following tasks:
1.	Installation of docker.io and python3-pip
2.	Virtual Memory increase to 262144
3.	Download and Launches Elk Docker Container
4.	Sets Public Ports
The following screenshot displays the result of running ‘sudo docker ps -a’ after successfully configuring the ELK instance.
DesignedandDeployedSecuredCloudNetworkwithElkStack-/Elk_Container_Running.png at main · bryanokelley/DesignedandDeployedSecuredCloudNetworkwithElkStack- (github.com)
Target Machines & Beats
This ELK server is configured to monitor the following machines:
- _TODO: List the IP addresses of the machines you are monitoring_

We have installed the following Beats on these machines:
- _TODO: Specify which Beats you successfully installed_

These Beats allow us to collect the following information from each machine:
- _TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc._

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned:

SSH into the control node and follow the steps below:
- Copy the _____ file to _____.
- Update the _____ file to include...
- Run the playbook, and navigate to ____ to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?_
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?_
- _Which URL do you navigate to in order to check that the ELK server is running?

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._
