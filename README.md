## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

https://github.com/BrettH78/Brett-s-Cyber-Bootcamp-Tasks/blob/main/Diagrams/Brett%20Red%20Team%20Azure%20Network%20Diagram.png

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. 

  - https://github.com/BrettH78/Brett-s-Cyber-Bootcamp-Tasks/blob/main/Ansible/Configure%20ELK%20Server%20with%20Docker%20YAMl%20Script.rtf

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly available, in addition to restricting external access to the network.
- Load Balancers add an extra layer of security by being able to block malicious IP's through Security Group rules and also being able direct traffic in the event of a DDOS attack. 
In the setup of this network I created a Jump Box which myself and other admins can connect to before being able to perform any administrative tasks within the enviroment.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the logs and system traffic.
- What does Filebeat watch for? Log files and their locations and logging of event data
- What does Metricbeat record? Collects metrics from systems and services. And directs them to an output that you specify.

The configuration details of each machine may be found below.
Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  | 10.0.0.4   | Unbuntu Linux    |
| Web 1    | DVWA     | 10.0.0.5   | Unbuntu Linux    |
| Web 2    | DVWA     | 10.0.0.6   | Unbuntu Linux    |
| Web 3    | DVWA     | 10.0.0.9   | Unbuntu Linux    |
| Elk VM   | Elk Stack| 10.1.0.5   | Unbuntu Linux    |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Jump Box machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- Home Machine Public IP address

Machines within the network can only be accessed by SSH.
- Which machine did you allow to access your ELK VM? What was its IP address? Virtual Jump Box 10.0.0.4

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes                 | Home Machine IP      |
| Web 1    | No                  | 10.0.0.4             |
| Web 2    | No                  | 10.0.0.4             |
| Web 3    | No                  | 10.0.0.4             |
| Elk VM   | No                  | 10.0.0.4             |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- What is the main advantage of automating configuration with Ansible? By adding multiple configurations into a single playbook that can be distributed to multiple machines.

The playbook implements the following tasks:
- In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
- Install docker.io
- Install python-pip
- Install docker
- 

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

https://github.com/BrettH78/Brett-s-Cyber-Bootcamp-Tasks/blob/main/Screentshots/image.png

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- List the IP addresses of the machines you are monitoring: VM1 10.0.0.5 VM2 10.0.0.6 VM3 10.0.0.9

We have installed the following Beats on these machines:
- Specify which Beats you successfully installed: Filebeat and Metricbeat were installed successfully on these machines

These Beats allow us to collect the following information from each machine:
- In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc. File collects log file changes and Metricbeat collects system information on hardware and services.

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the _____ file to _____.
- Update the _____ file to include...
- Run the playbook, and navigate to ____ to check that the installation worked as expected.

_ Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?_
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on? You update the hosts file on following path cd /etc/ansible/hosts. And add 3 Web VM's to webservers and create a a new heading for ELK server. Enter IP's and python line.
- Which URL do you navigate to in order to check that the ELK server is running? http://MyMachinePublicIP:5601

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc. ansible-playbook /etc/ansible/files/ansible-playbook.yml
