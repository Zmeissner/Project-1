## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![TODO: Update the path with the name of your diagram](Images/diagram_filename.png)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the _____ file may be used to install only certain pieces of it, such as Filebeat.

  - _TODO: Enter the playbook file._

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly recommended due to the fact that it distributes network or application traffic accross the 2 webservers, in addition to restricting access to the network.
- What aspect of security do load balancers protect? What is the advantage of a jump box? Load balancers protect from DDos attacks which works with availiblity aspect of security. The advantage of a jumpbox is that it is a secure computer that you connect to before launching an administrative task or use as an origination point to connect to onther servers.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the Webservers and system Metrics.
- What does Filebeat watch for? Filebeat watches for changes in Logs.
- What does Metricbeat record? Metricbeat records metrics and statistics.

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Functions  | IP Address                              | Operating system |
|----------|------------|-----------------------------------------|------------------|
| Jump Box | Gateway    | Private 10.0.04 | Public 40.76.8.43     | Linux            |
| Elk VM   | Log Server | Private 10.1.0.4 | Public 13.67.143.28  | Linux            |
| Web-1 VM | Webserver  | Private 10.0.0.5 | Public 20.124.249.41 | Linux            |
| Web-2 VM | Webserver  | Private 10.0.0.6 | Public 20.124.249.41 | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Jump Box machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
Whitelisted IP addresses 107.200.193.146/32 (My IP address)

Machines within the network can only be accessed by My IP through the Jump Box machine.
- Which machine did you allow to access your ELK VM? What was its IP address? Jump Box, Public IP 40.76.8.43 \ Private IP 10.0.0.4

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | No                  | 107.200.193.146/32   |
| Elk VM   | No                  | 10.0.0.4             |
| Web-1 VM | No                  | 10.0.0.4             |
| Web-2 VM | No                  | 10.0.0.4             |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- What is the main advantage of automating configuration with Ansible? Ansible helps with the representation of Infrastructure as code.

The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
- Increased Max memory, Needed this for elk to run
- Installed Docker.io onto, Used for running containers
- Installed python3-pip, Used to install Python software
- Downloaded the docker container sebp/elk:761
- Configured the container to start with 5601:5601, 9200:9200, and 5044:5044 Port mappings
- Enabled the container to start on boot

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![TODO: Update the path with the name of your screenshot of docker ps output](Images/Elk_Container_Running.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- List the IP addresses of the machines you are monitoring. Webserver 1-10.0.0.5 and Weberserver 2- 10.0.0.6

We have installed the following Beats on these machines:
- Specify which Beats you successfully installed. Filebeat and Metricbeat.

These Beats allow us to collect the following information from each machine:
- In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc._
Metricbeat allows us to monitor our cpu, load, memory usage, and network traffic. Metricbeat would be useful here to see if someone using up the network with a DDos attack.
Filebeat allows us to see logs. It would be useful to check these logs for seeing failed attempts to login to the webserver or failed SSH attempts.
### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the Install-elk.yml, filebeat-playbook.yml, and metricbeat-playbook.yml file to the ansible container. These are the playbooks you will need to run after setting up the config and host file.
- Update the /etc/host, Filebeat-config.yml, metricbeat-config.yml file to include the IP address of the Elk machine, and both webservers.
- Run the playbook, and navigate to Web-1 or Web-2 to check that the installation worked as expected.

_ Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?_ Filebeat-playbook.yml | Copy filebeat-playbook to your ansible container.
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on? You update the host file, filebeat-config.yml file, and the metricbeat-config.yml file. When creating the playbook for the elk server you need to specify the hosts to elk and for the Web-1 and Web-2 you need to make sure to use webservers for the hosts.
- _Which URL do you navigate to in order to check that the ELK server is running? You navigate to https://(Your_ELK_VM_IP):5601/app/kibana
