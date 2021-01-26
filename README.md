## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![TODO: Update the path with the name of your diagram](Images/DVWA.png)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the yml file may be used to install only certain pieces of it, such as Filebeat.

  [](Files/filebeat-playbook.yml)

  [](Files/metricbeat-playbook.yml)


This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly avaliable, in addition to restricting traffic to the network.
- Load balancing also plays an important security role as computing moves evermore to the cloud. The off-loading function of a load balancer defends an organization against **distributed denial-of-service (DDoS)** attacks. 
A **load balancer** can add additional layers of security to your website without any changes to your application. Protect applications from emerging threats 
- **Jump box** prevents all Azure VM’s to expose to the public. It can be set-up easily using ARM; We can do monitoring and logging on a single box. We can easily turn the ON/OFF remote desktop connectivity feature. By using the network security group, we can restrict the IP addresses to communicate with the Jump box.


Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the files and system usage.
- Filebeat collects data of the file system.
- Metricbeat collects machine metrics and system uptime.

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

In the first setup:
| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  | 10.0.0.4   | Linux            |
| Web-1    | Web WM 1 | 10.0.0.5   | Linux            |
| Web-2    | Web WM 2 | 10.0.0.6   | Linux            |
| Web-3    | Web WM 3 | 10.0.0.7   | Linux            |

Since we are using a free version, we could open have 3 VMs.
We will need to delete the Web-3 and then set up ELK Server.

| Name     | Function   | IP Address | Operating System |
|----------|------------|------------|------------------|
| Jump Box | Gateway    | 10.0.0.4   | Linux            |
| Web-1    | Web WM 1   | 10.0.0.5   | Linux            |
| Web-2    | Web WM 2   | 10.0.0.6   | Linux            |
| ELK      | ELK Server | 10.1.0.4   | Linux            |


### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Whitelisted machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses: 169.254.224.135

Machines within the network can only be accessed by SSH port.
My persaonl machine with IP 169.254.224.135 allow to access ELK VM.

A summary of the access policies in place can be found in the table below.

| Name          | Publicly Accessible |  Allowed IP Addresses      |   Location         |
|---------------|---------------------|----------------------------|--------------------|
| Jump Box      | Yes                 | SSH port 22                |   West US          |
| Web-1         | No                  | SSH port 22                |   West US          |
| Web-2         | No                  | SSH port 22                |   West US          |
| ELK           | Yes                 | 169.254.224.135            |   East US          |
| Load Blancer  | Yes                 | 169.254.224.135            |   West US          |


### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- _TODO: What is the main advantage of automating configuration with Ansible?_

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