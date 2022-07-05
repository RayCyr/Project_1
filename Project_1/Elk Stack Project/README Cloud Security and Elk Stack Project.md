## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.


![](https://github.com/RayCyr/Project_1/blob/main/Project_1/Elk%20Stack%20Project/Cloud%20Security%20Elk%20Stack%20Network%20Diagram/Cloud%20Security%20ELK%20Diagram.drawio.png)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. 

*[Ansible Configuration](https://github.com/RayCyr/Project_1/blob/main/Project_1/Elk%20Stack%20Project/Configuration%20Files/Ansible%20Configuration%20File.pdf)*

*[Ansible Hosts Configuration](https://github.com/RayCyr/Project_1/blob/main/Project_1/Elk%20Stack%20Project/Configuration%20Files/Ansible%20Hosts%20Configuration%20File.pdf)*

*[Playbook (Pentest.yml) ](https://github.com/RayCyr/Project_1/blob/main/Project_1/Elk%20Stack%20Project/Playbooks/Playbook%20(Pentest.yml%20).pdf)*




**Connect files that have been tested and used to generate a live ElK deployment**

Alternatively, select portions of the *etc/ansible* file may be used to install only certain pieces of it, such as Filebeat.

![Ansible](https://github.com/RayCyr/Project_1/blob/main/Project_1/Elk%20Stack%20Project/Ansible/Ansible.PNG)













  - _TODO: Enter the playbook file._

**This document contains the following details:**
* Description of the Topology
* Access Policies
* ELK Configuration
  * Beats in Use
  * Machines Being Monitored
* How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

**Load Balancing** 
* Restricts overload to the network.
* Load balancers protect availablity. 

**Jump box** 

* An advantage of a jumpbox is that a jumpbox *allows for the secure adminstration of web servers.*  

**Elk Server** 
* Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the _____ and system _____.

**Filebeat** 
* Filebeat watches for changes to files and when the changes were done.

**Metricbeat** 
* Records metrics from the operating system and from services running on a server.

**The configuration details of each machine may be found below.**

| **Name**     | **Function**                       | **IP Address**                                   | **Operating System**  |
|--------------|------------------------------------|--------------------------------------------------|-----------------------|
| Jump Box     | Gateway                            | Private IP: 10.0.0.4<br>Public  IP: 20.5.127.140 | Linux                 |
| Web 1        | Web Server                         | Private IP: 10.0.0.5                             | Linux                 |
| Web 2        | Web Server                         | Private IP: 10.0.0.6                             | Linux                 |
| Elk Server   | Monitors Web 1 & Web 2 Web Servers | Private IP: 10.1.0.4<br>Public  IP  20.37.0.17   | Linux                 |


### Access Policies

* The machines on the internal network are not exposed to the public Internet. 

* Only the "Jump Box Provisioner" machine can accept connections from the Internet. 
* Access to this machine is only allowed from the *IP addresses of the local host through SSH connection.*
    * A SSH key had to be generated from the local host and allowed access into the Jump Box Provisoner.
        * Allowing a server to use password authentication for SSH is insecure, because the password can be brute forced.
        * Only use cryptographic SSH keys.
    * The IP address of the local host for this project was 104.225.231.234.
![image](https://user-images.githubusercontent.com/98436629/177043139-7925236b-c794-458a-b371-75c2d838c09e.png)

* Machines within the network can only be accessed by the *local host* machine.

The *local host IP: 104.225.231.234* via SSH was allowed to access the ELK VM

**A summary of the access policies in place can be found in the table below.**



### Elk Configuration

* Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous, because.....(Need to find answer for this one)
 
* The main advantage of automating configuration with Ansible is that one module can be created and modified as needed and delployed to multiple VMs rather than having to configure each one seperately.

The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
- ...
- ...

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![TODO: Update the path with the name of your screenshot of docker ps output](Images/docker_ps_output.png)

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
