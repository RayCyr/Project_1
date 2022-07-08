## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![](https://github.com/RayCyr/Project_1/blob/main/Project_1/Elk%20Stack%20Project/Cloud%20Security%20Elk%20Stack%20Network%20Diagram/Cloud%20Security%20ELK%20Diagram.drawio.png)


These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above.Alternatively, select portions of the */etc/ansible* file may be used to install only certain pieces of it, such as Filebeat. 

*1) [Ansible](https://github.com/RayCyr/Project_1/blob/main/Project_1/Elk%20Stack%20Project/Ansible/Ansible.PNG)*

*2) [Ansible Configuration](https://github.com/RayCyr/Project_1/blob/main/Project_1/Elk%20Stack%20Project/Configuration%20Files/Ansible%20Configuration%20File.pdf)*

*3) [Ansible Hosts Configuration](https://github.com/RayCyr/Project_1/blob/main/Project_1/Elk%20Stack%20Project/Configuration%20Files/Ansible%20Hosts%20Configuration%20File.pdf)*

*4) [Playbook (Pentest.yml) ](https://github.com/RayCyr/Project_1/blob/main/Project_1/Elk%20Stack%20Project/Playbooks/Playbook%20(Pentest.yml%20).pdf)*

*5) [Playbook (install-elk.yml)](https://github.com/RayCyr/Project_1/blob/main/Project_1/Elk%20Stack%20Project/Playbooks/Playbook%20(install-elk.yml).pdf)*

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
* Restricts overload to the network
* Ensures availibity

**Jump box** 
* An advantage of a jumpbox is that a jumpbox *allows for the secure adminstration of web servers*.  

**ELK Server** 
* Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the *files and system metrics*.

**Filebeat** 
* Filebeat watches for changes to files and when the changes were done.

**Metricbeat** 
* Records metrics from the operating system and from services running on a server.

**The configuration details of each machine may be found below.**

| **Name**     | **Function**                       | **IP Address**                                      | **Operating System**  |
|--------------|------------------------------------|-----------------------------------------------------|-----------------------|
| Jump Box     | Gateway                            | Private IP: 10.0.0.4<br>Public  IP: 20.5.127.140    | Linux                 |
| Web 1        | Web Server                         | Private IP: 10.0.0.5                                | Linux                 |
| Web 2        | Web Server                         | Private IP: 10.0.0.6                                | Linux                 |
| Elk Server   | Monitors Web 1 & Web 2 Web Servers | Private IP: 10.1.0.4<br>Public IP 20.213.250.92:5601| Linux                 |


### Access Policies

* The machines on the internal network are not exposed to the public Internet. 

* Only the *Jump Box Provisioner* machine can accept connections from the Internet. 
* Access to this machine is only allowed from the *IP addresses of the local host through SSH connection.*
    * A SSH key had to be generated from the local host and allowed access into the Jump Box Provisoner.
        * Allowing a server to use password authentication for SSH is insecure, because the password can be brute forced.
        * Only use cryptographic SSH keys.
    * The IP address of the local host for this project was *104.225.231.234*.
![image](https://user-images.githubusercontent.com/98436629/177043139-7925236b-c794-458a-b371-75c2d838c09e.png)

* Machines within the network can only be accessed by the *Jummp Box Provisioner* machine.

The *Jump Box Provisioner IP: 10.0.0.4* is allowed to access the ELK VM

**A summary of the access policies in place can be found in the table below.**
| **Name**      | **Publicly Accessible**                                      | **Allowed IP Addresses**                                                 |
|---------------|--------------------------------------------------------------|--------------------------------------------------------------------------|
| Jump Box      | Yes<br>                                                      | IP: 104.255.231.234 (SSH)                                                |
| Web Server 1  | Yes<br><br>No<br><br>No- This is the IP of the load balancer | IP: 104.255.231.234 (SSH)<br><br>IP: 10.1.0.4<br><br>IP: 20.211.36.190   |
| Web Server 2  | Yes<br><br>No<br><br>No- This is the IP of the load balancer | IP: 104.255.231.234 (SSH)<br><br>IP: 10.1.0.4  <br><br>IP: 20.211.36.190 |
| Elk Server    | Yes<br><br>No                                                | IP: 104.225.231.234<br><br>IP: 10.0.0.4                                  |

**Additonal Newtwork Security Rules can be found below:

*1) [Jump Box Provisioner Sec Rules](https://github.com/RayCyr/Project_1/blob/main/Project_1/Elk%20Stack%20Project/Network%20Security%20Rules/Jump%20Box%20Provisioner%20Sec%20Rules.PNG)*



### Elk Configuration

* Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous, becacasue changes can be made to a playbook and delployed out to many other servers rather than having to configure each server seperately. 
 
**The playbook implements the following tasks:**

* 1 Install Docker
* 2 Install Python 3
* 3 Use more memory by setting the vm.max_map_count value to 262144
* 4 Download and launch a docker elk container with name elk and image sebp/elk:761
* 5 Enable sevice docker on reboot. 

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![](https://github.com/RayCyr/Project_1/blob/main/Project_1/Elk%20Stack%20Project/Docker_Elk/Confirm%20Docker_Elk_.PNG)*


### Target Machines & Beats

**This ELK server is configured to monitor the following machines:**

* Web 1 10.0.0.5
* Web 2 10.0.0.6

**We have installed the following Beats on these machines:**
* Filebeat
* Metricbeat

**These Beats allow us to collect the following information from each machine:**

* Filebeat creates logs files from very specific files, such as logs generated by Apache, Microsoft Azure tools, the Nginx web server, or MySQL databases.
* Metricbeat collects metrics from the system and services running to include CPU Usage, Load, Memory Usage, Inbound Received bit/s and Outbound Transfer bits/s. 


### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
* Copy the *Configuration file to Web1 & Web2 for each Filebeat and Metricbeat to /etc/filebeat/filebeat.yml and the same for metricbeat*
- Update the _____ file to include...
- Run the playbook, and navigate to ____ to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?_
- _Which file do you update to make Ansible run the playbook on a specific machine? 
- 
- How do I specify which machine to install the ELK server on versus which to install Filebeat on?_
- 
**To verify that the ELK server was running, navigation to the URL below was necessary.** 

* **Example format:** http://[VM.ip/:5601/app/kibana

* **Actual for this project:** http://20.213.250.92/:5601/app/kibana 

 
_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._
