## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![Cloud Security Network Diagram](https://github.com/RayCyr/Project_1/blob/main/Project_1/Cloud_Security_Project/Cloud_Security_Network_Diagram/Cloud%20Sec%20Network%20Diagram.drawio.png)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the _____ file may be used to install only certain pieces of it, such as Filebeat.

  - _TODO: Enter the playbook file._

This document contains the following details
* Description of the Topology
* Access Policies
* ELK Configuration
  * Beats in Use
  * Machines Being Monitored
* How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.
Load balancing ensures that the application will be highly **available**, in addition to restricting **overload** to the network.
Load balancers protect **availablity** 

**Jump Box**
* The advantage of a jump box is a jumpbox allows for the **secure adminstration of web servers.**  

**Elk Server**
* Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the _____ and system _____.

**Filebeat**
* Filebeat watches for changes to files and when the changes were done.

**Metricbeat**
* Metricbeat records metrics from the operating system and from services running on a server.

The configuration details of each machine may be found below.
         
| Name         | Function                           | IP Address                                       | Operating System  |
|--------------|------------------------------------|--------------------------------------------------|-------------------|
| Jump Box     | Gateway                            | Private IP: 10.0.0.4<br>Public  IP: 20.5.127.140 | Linux             |
| Web 1        | Web Server                         | Private IP: 10.0.0.5                             | Linux             |
| Web 2        | Web Server                         | Private IP: 10.0.0.6                             | Linux             |
| Elk Server   | Monitors Web 1 & Web 2 Web Servers | Private IP: 10.1.0.4<br>Public  IP  20.37.0.17   | Linux             |




















### Elk Configuration

**Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because __
The main advantage of automating configuration with Ansible**

The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
- ...
- ...

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![TODO: Update the path with the name of your screenshot of docker ps output](Images/docker_ps_output.png)

### Target Machines & Beats

**This ELK server is configured to monitor the following machines:**
* Web 1 10.0.0.5        
* Web 2 10.0.0.6
 
**The following Beats were installed on these machines:**
* Filebeat
* Metricbeat

**These Beats allow us to collect the following information from each machine:

* Filebeat collects data about specific files on remote machines. For example, Filebeat collects Apache logs, Microsoft Azure tools or MySQL databases. 

* Metricbeat collects metrics for remote machines. For example, one would expect to see the following for the given VMs.
  * CPU Usage
  * Load
  * Memory Usage
  * Inbound RX -Displays the amount of received data (kbits/s)
  * Outbound TX -Displays the amount of transferred data) (kbits/s)
  

### Using the Playbook
* In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

### SSH into the control node and follow the steps below:
   1. Copy the _____ file to _____.
   1. Update the _____ file to include...
   1. Run the playbook, and navigate to ____ to check that the installation worked as expected.


- _Which file is the playbook? Where do you copy it?_
- 
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?_

* Navigate to the Kibana URL with the format of:[http://[your.VM.IP]:5601/app/kibana] order to check that the ELK sever is running.
 

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._
