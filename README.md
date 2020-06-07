# literate-octo-computing-machine
## Automated ELK Stack Deployment
The files in this repository were used to configure the network depicted below.

Azure Virtual Network
https://drive.google.com/open?id=1kTJXmw-3NKsgpjFoNKwRoQWike8b3whq
These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the playbook file may be used to install only certain pieces of it, such as Filebeat.
  - filebeat-playbook.yml
This document contains the following details:
- Description of the Topology
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build

### Description of the Topology
The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.
Load balancing ensures that the application will be highly stable, in addition to restricting access to the network.
- Load balancers protect the site if a server goes down it will remain up. Jump boxes have hardened security to protect the containers set up within it. 
Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the files and system metrics.
- What does Filebeat watch for?_Log files or specified locations
- What does Metricbeat record?_Metrics and services on the server and OS
The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.
| Name       | Function        | IP Address    | Operating System |
|------------|-----------------|---------------|------------------|
| ELK-Stack  | Gateway         | 137.135.28.33 | Linux            |   
| RedTeam-LB | Load Balancer   | 13.88.9.25    | Linux            |   
| DVWA-VM1   | Virtual Machine | 10.0.0.5      | Linux            |   
| DVWA-VM2b  | Virtual Machine | 10.0.0.7      | Linux            |   


### Access Policies
The machines on the internal network are not exposed to the public Internet. 
Only the jumpbox/elk-stack machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- 73.164.51.78
Machines within the network can only be accessed by the jumpbox/elk-stack.
- _TODO: Which machine did you allow to access your ELK VM? What was its IP address?_
A summary of the access policies in place can be found in the table below.
| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes/No              | 10.0.0.1 10.0.0.2    |
|          |                     |                      |
|          |                     |                      |

### Elk Configuration
Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- Easy to configure and can be used with multiple VMs at a time
The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc.
- Install docker.io
- Install python-pip
- Launch docker container
The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.
![TODO: Update the path with the name of your screenshot of docker ps output](Images/docker_ps_output.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- 10.0.0.5, 10.0.0.7
We have installed the following Beats on these machines:
- Filebeat
These Beats allow us to collect the following information from each machine:
- In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. 
Filebeat collects log files, and Metricbeat collects host metrics

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 
SSH into the control node and follow the steps below:
- Copy the _____ file to _____.
- Update the _____ file to include...
- Run the playbook, and navigate to ____ to check that the installation worked as expected.
_TODO: Answer the following questions to fill in the blanks:
- _Which file is the playbook? Where do you copy it?
Then pentest.yml playbook will setup the VM, and the filebeat-playbook.yml will install filebeat. 
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on? 
You will update the hosts file and put the ip address of the machine you want to install on. 
- _Which URL do you navigate to in order to check that the ELK server is running?
http://137.135.28.33:5601/

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._
