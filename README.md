## Project-13
Automated ELK Stack Deployment - Azure

This document contains the following details:
- Description of the Topology
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build

The files in this repository were used to configure the network depicted below.

![Diagram/Project-13 ELK Network Diagram.png](https://github.com/ShinHJP/Project-13/blob/main/Diagram/Project-13%20ELK%20Network%20Diagram.png)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the yml and config file may be used to install only certain pieces of it, such as Filebeat.

### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly stable, in addition to restricting traffic to the network.
- What aspect of security do load balancers protect? What is the advantage of a jump box?
    The off-loading function of a load balancer defends an organization against distributed denial-of-service (DDoS) attacks. The main advantage to having a jump box is to have added layer of protection Multifactor Authentication (MFA)

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the log and system files.
- What does Filebeat watch for?
    Filebeat watches for data about the file system.
- What does Metricbeat record?


The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name       | Function | IP Address | Operating System |
|------------|----------|------------|------------------|
| Jump Box   | Gateway  | 10.0.0.4   | Linux            |
| Web-1      | Client   | 10.0.0.5   | Linux            |
| Web-2      | Client   | 10.0.0.6   | Linux            |
| Web-3      | Client   | 10.0.0.7   | Linux            |
| ELK-SERVER | Client   | 10.1.0.4   | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet.

Only the Jump-Box machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- Add whitelisted IP addresses:
    168.61.182.23

Machines within the network can only be accessed by SSH from the Jump-Box VM.
- Which machine did you allow to access your ELK VM? What was its IP address?
    Jump-Box can access the ELK-SERVER private IP is 10.2.0.4

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes                 | 168.61.182.23        |
| ELK      | No                  | 10.1.0.0-254         |
| Web-1    | No                  | 10.0.0.1-254         |
| Web-2    | No                  | 10.0.0.1-254         |
| Web-3    | No                  | 10.0.0.1-254         |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- What is the main advantage of automating configuration with Ansible?
    The main advantage is configuration management and provisioning.

The Playbook Implementations through the following tasks:  
  - .Install docker
  - .Install pip3
  - .Install docker python module
  - .Increase and set memory to 262144
  - .Download and launch docker elk container:761

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![/Images/Docker_ps.PNG](https://github.com/ShinHJP/Project-13/blob/main/Images/Docker_ps.PNG)

![/Images/Install_ELK_Playbook.PNG](https://github.com/ShinHJP/Project-13/blob/main/Images/Install_ELK_Playbook.PNG)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
  - Web-1: 10.0.0.5
  - Web-2: 10.0.0.6
  - Web-3: 10.0.0.7
  - ELK-SERVER: 10.1.0.4

We have installed the following Beats on these machines:

These Beats allow us to collect the following information from each machine:
- Filebeat - Filebeat monitors the log files or locations that you specify, collects log events, and forwards them either to Elasticsearch or Logstash for indexing

The playbook below installs Filebeat on the target hosts.

![/Ansible/filebeat-playbook.yml](https://github.com/ShinHJP/Project-13/blob/main/Ansible/filebeat-playbook.yml)


### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned:

SSH into the control node and follow the steps below:
- Copy the playbook file to /etc/ansible.
- Update the hosts file to include each vm client IP address
    - 10.0.0.5 ansible_python_interpreter=/usr/bin/python3
    - 10.0.0.6 ansible_python_interpreter=/usr/bin/python3
    - 10.0.0.7 ansible_python_interpreter=/usr/bin/python3

- Run the playbook, and navigate to 10.1.0.4 and curl localhost/setup.php to check that the installation worked as expected..

- Which file is the playbook? Where do you copy it?
    - Ansible-playbook.yml
    - /etc/ansible
- Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?
    - It is updated on the hosts file, add hosts name elk into the webservers group followed by the IP address for the ELK-SERVER in this case 10.1.0.4 /Ansible/hosts.txt

    ![/Ansible/hosts.txt](https://github.com/ShinHJP/Project-13/blob/main/Ansible/hosts.txt)

- Which URL do you navigate to in order to check that the ELK server is running?
    - Public IP address on port 5601/app (104.42.108.35:5601/app)
    - Kabana Application

Specific commands to run to download the playbook and update the files.
- ansible-playbook *.yml nano hosts nano ansible.cfg nano *.yml
