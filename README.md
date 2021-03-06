## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![Network diagram](https://github.com/shonham/Shontae-s-Cybersecurity-Project-1/blob/8e67b9f1d26e72db8c7ba8ac17c53083eea6f9b5/diagrams/Network%20diagram.png)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the _____ file may be used to install only certain pieces of it, such as Filebeat.

  [elk-playbook](https://github.com/shonham/Shontae-s-Cybersecurity-Project-1/blob/a7aa16cf635a87bcdcdc3475a98223c9344a9578/ansible/elk-playbook.yml)

[filebeat-playbook](https://github.com/shonham/Shontae-s-Cybersecurity-Project-1/blob/a70586b1eed01873d6c168f6c6f7267a0571bb90/ansible/filebeat-playbook.yml)

[hosts](https://github.com/shonham/Shontae-s-Cybersecurity-Project-1/blob/ae948cf639794aa9497d8730318f2b50798dcdd8/ansible/hosts.yml)

[metric-playbook](https://github.com/shonham/Shontae-s-Cybersecurity-Project-1/blob/ae948cf639794aa9497d8730318f2b50798dcdd8/ansible/metric-playbook.yml)

[pentest](https://github.com/shonham/Shontae-s-Cybersecurity-Project-1/blob/fce05cf5ebd2e7182719ca0a069910dc37ccf4d8/ansible/pentest.yml)





This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly available, in addition to restricting access to the network.
- What aspect of security do load balancers protect? 
- By shifting traffic, load balancers protect the system against DDoS attacks.
- 
- What is the advantage of a jump box?_
- A jump box has the advantage of providing secure access to such resources via SSH and a private pre-shared key.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the data and system logs
- What does Filebeat watch for?
- -Filebeat consolidates and sends log data. Filebeat collects log events from the log files or places you choose and sends them to Elasticsearch or Logstash for indexing.
- 
- What does Metricbeat record?
- -Metricbeat collects metrics and data and sends them to the destination you select, such as Elasticsearch or Logstash. Metricbeat collects information from the system and services operating on the server, such as Apache, to help you manage your servers.

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  10.1.0.4     | Linux            |
| Elk      | Gateway  | 40.78.3.115| Linux            |
| Web-1    | LBalancer| FTE-IP     | Linux            |
| Web-2    | LBalancer| FTE-IP     | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Elk machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- 45.23.180.71

Machines within the network can only be accessed by Jumpbox via SSH & Private Pre-Shared key
- Which machine did you allow to access your ELK VM?
- Jumpbox
- 
-  What was its IP address?_
-  40.113.205.32 (public) 10.1.0.4 (private)

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes                 | 45.23.180.71         |
|          |                     |                      |
|          |                     |                      |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
What is the main advantage of automating configuration with Ansible?
- Configuration management, single source for application deployment

The playbook implements the following tasks:
- In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
- Check for presence of docker (Installation/Update)
- Check for presence of python3-pip (Install/Update)
- Install Docker module
- Increase virtual memory
- Download and launch docker elk container

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![Docker ps](https://github.com/shonham/Shontae-s-Cybersecurity-Project-1/blob/8573356a371266d9c31bd00b2386bedb29c34ddd/diagrams/Docker%20ps.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- Web-1 10.1.0.5 
- Web-2 10.1.0.6

We have installed the following Beats on these machines:
-Webservers

These Beats allow us to collect the following information from each machine:
-Machine health, performance, system logs and events

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the filebeat file to file-config.yml
- Update the filebeat.yml file to include...
- Run the playbook, and navigate to check that the installation worked as expected.
![kibanaserver](https://github.com/shonham/Shontae-s-Cybersecurity-Project-1/blob/60d84b78333fafae4d4bba4a4df2463d74c25476/diagrams/kibanaserver.png)

Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Ansible-playbook files
- Where do you copy it? Root of ansible
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on? hosts configuration file

Which URL do you navigate to in order to check that the ELK server is running? 
-ssh azureuser@10.1.0.5
-http://40.78.3.115:5601/app/kibana

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._
![Ansible-Playbook_NAME_OF_PLAYBOOK](https://github.com/shonham/Shontae-s-Cybersecurity-Project-1/blob/b2a066b6d60976971ca5962ce6437c457b3a3711/diagrams/Ansible-Playbook_NAME_OF_PLAYBOOK.png)

![Ansible-Playbook_NAME_OF_PLAYBOOK]
ssh azureuser@40.113.205.32
sudo docker container list -a
sudo docker start (name)
sudo docker attach (name)
cd /etc/ansible
ls
nano metric-playbook.yml

