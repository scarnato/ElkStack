## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![](diagrams/PostElk%20Diagram.png)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the ansible playbook file may be used to install only certain pieces of it, such as Filebeat.


This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the Damn Vulnerable Web Application.

Load balancing ensures that the application will be highly secure and monitored, in addition to restricting outside access to the network.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the log files and system files.

The configuration details of each machine may be found below.

| Name       | Function | Ip Address | Operating System |
|------------|----------|------------|------------------|
| Jump Box   | Gateway  | 10.0.0.4   | Linux            |
| Elk Server | Filebeat | 10.1.0.4   | Linux            |
| Web 1      | DVWA     | 10.0.0.7   | Linux            |
| Web 2      | DVWA     | 10.0.0.6   | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the jump box virtual machine can accept connections from the Internet. Access to this machine is limited through the RedTeam security group to only the local workstations ipv4 address.

The other machines on the network, web 1, web 2, and the elk server, only accept connections from the jump box machine.

A summary of the access policies in place can be found in the table below.

| Name       | Publicly Accessible | Allowed IP Adresses |
|------------|---------------------|---------------------|
| Jump Box   | Yes                 | Local ipv4          |
| Elk Server | No                  | 10.0.0.4            |
| Web 1      | No                  | 10.0.0.4 / 10.1.0.4 |
| Web 2      | No                  | 10.0.0.4 / 10.1.0.4 |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous over any situation which requires setup on more than one machine, saving a great amount of time.

The elk installation playbook implements the following tasks:
- Install docker.io
- Install pip3
- Install docker python module
- Increase amount of memory on the virtual machine

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![](ansible/Images/docker%20ps.PNG)

### Target Machines & Beats
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
