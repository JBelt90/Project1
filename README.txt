# Project1 ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

!(Diagrams/ELK Project - Virtual Network Cloud Diagram.jpg)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the README.md file may be used to install only certain pieces of it, such as Filebeat.

  - ansible.cfg

This document contains the following details:
- Description of the Topology
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly secured, in addition to restricting traffic to the network.
- Load balancers protects the system from DDoS attacks by shifting attack traffic. The advantage of a jump box is to give access to the user from a single node that can be secured and monitored.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the CPU and system memory.
- Filebeat is a lightweight shipper for forwarding and centralizing log data, and monitors the log files or locations that you specify, collects log events, and forwards them either to Elasticsearch or Logstash for indexing.
- Metricbeat is a lightweight shipper that you can install on your servers to periodically collect metrics from the operating system and from services running on the server. Metricbeat takes the metrics and statistics that it collects and ships them to the output that you specify, such as Elasticsearch or Logstash.

The configuration details of each machine may be found below.


| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  | 10.0.0.4   | Linux            |
| Web 1    |Web Server| 10.0.0.5   | Linux            |
| Web 2    |Web Server| 10.0.0.6   | Linux            |
|          |          |            |                  |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Jump Box machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- 191.96.121.151

Machines within the network can only be accessed by 20.94.229.205.


A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes                 | 10.0.0.5 10.0.0.6    |
|          |                     |                      |
|          |                     |                      |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- Automated configuration with Ansible is free, fast, and secure.

The playbook implements the following tasks:
- Config ELK VM with Docker
- Install Docker.io
- Install python3
- Install Docker module
- Increase virtual memory on restart
- Enable service Docker on boot

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

! (Images/Docker prompt)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- 10.0.0.5 10.0.0.6

We have installed the following Beats on these machines:
- Filebeat, Metricbeat

These Beats allow us to collect the following information from each machine:
- Operating System metrics from services running on the server, log files, collect log events.

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the .cfg file to /ansible.
- Update the .cfg file to include the playbook
- Run the playbook, and navigate to the home directory to check that the installation worked as expected.
