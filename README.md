## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![](https://github.com/Josephogiste/Project-Microsoft-Azure-ELK-ANSIBLE-DOCKER-DVM/blob/master/NETWORK%20DIAGRAM.png)

These files have been tested and used to generate a live ELK deployment on Microsoft Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the file may be used to install only certain pieces of it, such as Filebeat.

dockerplaybook.yml
[a link](https://github.com/Josephogiste/Project-Microsoft-Azure-ELK-ANSIBLE-DOCKER-DVM/blob/master/dockerplaybook.yml)

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly responsive, in addition to restricting unauthorized access to the network, this
prevents (DDoS) Denial of Service attacks from occurring. Traffic is shifted from the company's server to a cloud provider.
It also increases availability of applications and websites for users. Modern applications cannot run without load balancers.
Load balancers rest on the layer 7 of the security OSI layers (Application layer)

- What is the advantage of a jump box?
  A Jumpbox allows users to connect into the virtual network from an external source gaining access to internal servers/networks via a private IP address.
  This protects both the user and the cooperation from attacks.

- Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the _____ and system _____.
- What does Filebeat watch for?
  Filebeat is used for the monitoring of log files or locations that are specified and also collect log events and forward
  them to either Elasticsearch or Logstash for archive.
- What does Metricbeat record?
  Metricbeat collects the metrics and statistics of operating systems and ships them to either Elasticsearch or Logstash.
  
The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     |      Function    | IP Address | Operating System |
|----------|------------------|------------|------------------|
| Jump Box |  Main Gateway    | 10.0.0.4   | Ubuntu 18.04     |
| WEB-1    |  Virtual Machine | 10.0.0.5   | Ubuntu 18.04     |
| WEB-2    |  Virtual Machine | 10.0.0.7   | Ubuntu 18.04     |
| ELK      |  Virtual Machine | 10.1.0.4   | Ubuntu 18.04     |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Jump Box machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses: "my prvate IP and 10.0.0.4"

Machines within the network can only be accessed by SSH via TCP.
The ELk machine was allowed access via the Jump Box machinevia 10.0.0.4. and was only allowed access via port 5601.

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible   | Allowed IP Addresses      |
|----------|-----------------------|---------------------------|
| Jump Box | YES                   | Registered Private IP     |
| WEB-1    | NO                    | Private IP,10.0.0.4       |
| WEB-2    | NO                    | Private IP,10.0.0.4       |
| ELK      | YES via.5601/9200/5044| 10.0.0.4/10.0.0.5/10.0.0.7|

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because
it eliminates the the chance of human error and also can run from the command line for updates and sepcific configurations allowing large organisations to 
run more smoothly. It is fast paced and requires no installation agent.

The playbook implements the following tasks:
- User SSH 'ed into Jump-Box
- Docker was installerd with the command 'sudo apt-get install docker.io bash' via gitbash.
  a list was then obtained via command 'sudo docker container list -a'. the ansible container was
  then started and attached.
- The ELK ansible playbook was then formatted and created in the container.
- After successfully creating the ELk playbook, it was launched and configurations were made on 
  the cloud service.

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![sudo dokcer ps:https://drive.google.com/file/d/1SbEfSKr6ezePUDpfwTApVfVgyxXoDcTi/view?usp=sharing

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
WEB-1/10.0.0.5 and WEB-2/10.0.0.7

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
