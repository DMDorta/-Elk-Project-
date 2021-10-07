## **Automated ELK Stack Deployment** 



The files in this repository were used to configure the network depicted below. 

![BOOTCAMP-Finished-Cloud-Diagram](https://user-images.githubusercontent.com/85771952/136270986-f3ca1f0f-200a-493e-a245-d7fa01fd4392.png)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to recreate the entire deployment pictured above. Alternatively, select the file(s) that are used to install only certain pieces of it, such as Filebeat. 

[Install_Elk.yml](https://github.com/DMDorta/X-Cybersecurity-X/blob/main/Ansible/Install_Elk.yml)

### **This document contains the following details:** 
\- Description of the Topology 
\- Access Policies 
\- ELK Configuration 
\- Beats in Use 
\- Machines Being Monitored 
\- How to Use the Ansible Build 

## **Description of the Topology** 

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application. 

-Load balancing ensures that the application will be highly responsive, in addition to restricting access to the network. The off-loading function of load balancers aid in protecting an organization against DDoS attacks.  

-A jump box is useful to reduce unauthorized access to networks and make connections more secure. 

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the log files and system performance.

- **Filebeat**  monitors and collects log files and events data to be cataloged by *Elasticsearch* or *Logstash*.
- **Metricbeat** collects metrics and statistics of services running and transfers data to specified output such as *Elasticsearch* or *Logstash*.

The configuration details of each machine may be found below. 


| Name     | Function  | IP Address | Operating System |
| -------- | --------- | ---------- | ---------------- |
| Jump-Box | Gateway   | 10.0.0.5   | Linux            |
| Web-1    | VM        | 10.0.0.6   | Linux            |
| Web-2    | VM        | 10.0.0.7   | Linux            |
| Web-3    | VM        | 10.0.0.8   | Linux            |
| Elk-VM   | Elk-Stack | 10.1.0.4   | Linux            |
|          |           |            |                  |

## **Access Policies** 

The machines on the internal network are not exposed to the public Internet. 

Only the Jump-Box machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses: 

- 212.102.44.87

Machines within the network can only be accessed by Port 22. 

- Jump-Box - 10.0.0.5

A summary of the access policies in place can be found in the table below. 

| Name     | Publicly Accessible     | Allowed IP Addresses    |
| -------- | ----------------------- | ----------------------- |
| Jump Box | No                      | local machine           |
| Elk-VM   | No                      | local machine, 10.0.0.5 |
| Web-1    | Yes (via Load Balancer) | any IP via http         |
| Web-2    | Yes (via Load Balancer) | any IP via http         |
| Web-3    | Yes (via Load Balancer) | any IP via http         |
|          |                         |                         |

## **Elk Configuration** 

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because... 

- Ansible simplifies repetitive, sophisticated, and tedious operations. 

The playbook implements the following tasks: 

- Install docker.io

- Install python-pip

- Install docker python module
- Increase virtual memory

- Download and launch a docker elk stack
- Enable service docker on boot

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance. 

[![docker_ps](https://user-images.githubusercontent.com/85771952/136271074-ffbe9dca-5493-4676-9b4a-681825cac775.png)](~/Projects/X-Cybersecurity-X/Images/docker_ps.png) 

## **Target Machines & Beats** 

This ELK server is configured to monitor the following machines: 

- 10.0.0.6

- 10.0.0.7

- 10.0.0.8

We have installed the following Beats on these machines: 
Filebeat and Metricbeat

These Beats allow us to collect the following information from each machine: 
Filebeat  is used for log analysis and Metricbeat periodically collect metrics from the operating system and from services running on the server.

## Using the Playbook 
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:

- Copy install-elk.yml to /etc/asible

- Update the hosts file to include the Elk IP 

- Run the playbook, and navigate to Kibana webpage to check that the installation 	worked as expected. 

- Copy the config files to corresponding configuration directory in Elk

- Update hosts file for each specific machine

-  Specify host in config file


_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._ 

