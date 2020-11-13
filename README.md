# Portfolio
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

Load balancing ensures that the application will be highly _____, in addition to restricting _____ to the network.
- _TODO: What aspect of security do load balancers protect? What is the advantage of a jump box?_
load balancer adds layers to your security. Jump box allows admins to connect first or origin point of connection with untrusted enviroment
Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the _____ and system _____.
- _TODO: What does Filebeat watch for?_
 where all the log files are
- _TODO: What does Metricbeat record?_
it collect and ships the statics

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  | 10.0.0.1   | Linux            |
| TODO     |          |            |                  |
| TODO     |          |            |                  |
| TODO     |          |            |                  |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the ___mv__ machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- _TODO: Add whitelisted IP addresses_

Machines within the network can only be accessed by _____.
- _TODO: Which machine did you allow to access your ELK VM? What was its IP address?_

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes/No              | 10.0.0.1 10.0.0.2    |
|          |                     |                      |
|          |                     |                      |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- _TODO: What is the main advantage of automating configuration with Ansible?_

The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
- do a vm for elk use same network team, public ip, cat  id_rsa.pub copy and paste
- 

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.
root@40e19f1817ea:/etc/ansible/files# ansible-playbook install-elk.yml

PLAY [Configure Elk VM with Docker] ********************************************************************

TASK [Gathering Facts] *********************************************************************************
ok: [10.1.0.4]

TASK [Install docker.io] *******************************************************************************
changed: [10.1.0.4]

TASK [Use more memory] *********************************************************************************
changed: [10.1.0.4]

TASK [Increase virtual memory] *************************************************************************
changed: [10.1.0.4]

TASK [Install python3-pip] *****************************************************************************
changed: [10.1.0.4]

TASK [Install Docker module] ***************************************************************************
changed: [10.1.0.4]

TASK [download and launch a docker elk container] ******************************************************
changed: [10.1.0.4]

PLAY RECAP *********************************************************************************************
10.1.0.4                   : ok=7    changed=6    unreachable=0    failed=0    skipped=0    rescued=0



![TODO: Update the path with the name of your screenshot of docker ps output](Images/docker_ps_output.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- _TODO: List the IP addresses of the machines you are monitoring_
10.0.0.10
10.0.0.8

We have installed the following Beats on these machines:
- _TODO: Specify which Beats you successfully installed_
root@40e19f1817ea:/etc/ansible/roles# ansible-playbook filebeat-playbook.yml

PLAY [Configure the filebeat] ****************************************************************************************************************

TASK [Gathering Facts] ***********************************************************************************************************************
The authenticity of host '10.0.0.8 (10.0.0.8)' can't be established.
ECDSA key fingerprint is SHA256:XjXTouoS7uY3Mu20/11c6LEDyhcHOeO+9J8Lw56DlwM.
Are you sure you want to continue connecting (yes/no)? The authenticity of host '10.0.0.10 (10.0.0.10)' can't be established.
ECDSA key fingerprint is SHA256:5cf84kYu/Xxext0rPevBicztXUtRiadNwnmmOu4k+Wg.
Are you sure you want to continue connecting (yes/no)? y
fatal: [10.0.0.10]: UNREACHABLE! => {"changed": false, "msg": "Failed to connect to the host via ssh: Host key verification failed.", "unreachable": true}
yes
Please type 'yes' or 'no': yes
fatal: [10.0.0.8]: UNREACHABLE! => {"changed": false, "msg": "Failed to connect to the host via ssh: Warning: Permanently added '10.0.0.8' (ECDSA) to the list of known hosts.\r\nGramirez@10.0.0.8: Permission denied (publickey).", "unreachable": true}

PLAY RECAP ***********************************************************************************************************************************
10.0.0.10                  : ok=0    changed=0    unreachable=1    failed=0    skipped=0    rescued=0    ignored=0
10.0.0.8                   : ok=0    changed=0    unreachable=1    failed=0    skipped=0    rescued=0    ignored=0


These Beats allow us to collect the following information from each machine:
- _TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc._

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the _____ file to _____.
- Update the _____ file to include...
- Run the playbook, and navigate to _ansible_playbook filebeat-playbook.yml___ to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?_
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?_
- _Which URL do you navigate to in order to check that the ELK server is running?

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._





Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '13.66.130.36' (ECDSA) to the list of known hosts.
Welcome to Ubuntu 18.04.5 LTS (GNU/Linux 5.4.0-1031-azure x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

  System information as of Fri Nov 13 02:26:42 UTC 2020

  System load:  0.05              Processes:           118
  Usage of /:   6.8% of 28.90GB   Users logged in:     0
  Memory usage: 23%               IP address for eth0: 10.0.0.4
  Swap usage:   0%

 * Introducing self-healing high availability clustering for MicroK8s!
   Super simple, hardened and opinionated Kubernetes for production.

     https://microk8s.io/high-availability

12 packages can be updated.
0 updates are security updates.


Last login: Sat Nov  7 17:47:17 2020 from 99.70.111.115
Gramirez@JUMPBOX:~$ sudo systemctl status docker
● docker.service - Docker Application Container Engine
   Loaded: loaded (/lib/systemd/system/docker.service; disabled; vendor preset:
   Active: inactive (dead)
     Docs: https://docs.docker.com
Gramirez@JUMPBOX:~$ sudo systemctl start docker
Gramirez@JUMPBOX:~$ sudo docker container list -a
CONTAINER ID        IMAGE                           COMMAND             CREATED             STATUS                  PORTS               NAMES
40e19f1817ea        cyberxsecurity/ansible:latest   "bash"              7 days ago          Exited (0) 5 days ago                       goofy_mayer
Gramirez@JUMPBOX:~$ sudo docker start goofy_mayer
goofy_mayer
Gramirez@JUMPBOX:~$ sudo docker attached goofy_mayer
docker: 'attached' is not a docker command.
See 'docker --help'
Gramirez@JUMPBOX:~$ sudo docker attach goofy_mayer
root@40e19f1817ea:~# ssh Gramirez@40.121.153.28
The authenticity of host '40.121.153.28 (40.121.153.28)' can't be established.
ECDSA key fingerprint is SHA256:uzSAqMMU4hYHt64JENfDqH0Pwpcb+IqZSkTe0doy0j8.
Are you sure you want to continue connecting (yes/no)? yes
Warning: Permanently added '40.121.153.28' (ECDSA) to the list of known hosts.
Welcome to Ubuntu 18.04.5 LTS (GNU/Linux 5.4.0-1031-azure x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

  System information as of Fri Nov 13 02:31:57 UTC 2020

  System load:  0.08              Processes:           117
  Usage of /:   4.7% of 28.90GB   Users logged in:     0
  Memory usage: 5%                IP address for eth0: 10.1.0.4
  Swap usage:   0%

 * Introducing self-healing high availability clustering for MicroK8s!
   Super simple, hardened and opinionated Kubernetes for production.

     https://microk8s.io/high-availability

11 packages can be updated.
0 updates are security updates.


Last login: Sat Nov  7 19:47:18 2020 from 10.0.0.4

Gramirez@ELK:~$
Gramirez@ELK:~$ q

Command 'q' not found, but can be installed with:

sudo snap install q                       # version 1.6.3-1, or
sudo apt  install python-q-text-as-data
sudo apt  install python3-q-text-as-data

See 'snap info q' for additional versions.

Gramirez@ELK:~$ exit
logout
Connection to 40.121.153.28 closed.
root@40e19f1817ea:~#
root@40e19f1817ea:~# cd /etc
root@40e19f1817ea:/etc# cd ansible
root@40e19f1817ea:/etc/ansible# ls
ansible.cfg  files  hosts  my-playbook.yml  roles
root@40e19f1817ea:/etc/ansible# nano hosts
root@40e19f1817ea:/etc/ansible# nano ansible.cfg
root@40e19f1817ea:/etc/ansible# cd files
root@40e19f1817ea:/etc/ansible/files# ls
install-elk.yml
root@40e19f1817ea:/etc/ansible/files# ansible-playbook install install-elk.yml
ERROR! the playbook: install could not be found
root@40e19f1817ea:/etc/ansible/files# ansible-playbook install -elk.yml
ERROR! the playbook: install could not be found
root@40e19f1817ea:/etc/ansible/files# ansible-playbook install-elk.yml
ERROR! Syntax Error while loading YAML.
  did not find expected '-' indicator

The error appears to be in '/etc/ansible/files/install-elk.yml': line 4, column 3, but may
be elsewhere in the file depending on the exact syntax problem.

The offending line appears to be:

   command: sysctl -w vm.max_map_count="262144"
  - name: Install python3-pip
  ^ here

root@40e19f1817ea:/etc/ansible/files# nano install-elk.yml
root@40e19f1817ea:/etc/ansible/files# ansible-playbook install-elk.yml
ERROR! Syntax Error while loading YAML.
  mapping values are not allowed in this context

The error appears to be in '/etc/ansible/files/install-elk.yml': line 5, column 8, but may
be elsewhere in the file depending on the exact syntax problem.

The offending line appears to be:

   -name: Install python3-pip
    apt:
       ^ here

root@40e19f1817ea:/etc/ansible/files# nano install-elk.yml
root@40e19f1817ea:/etc/ansible/files# ansible-playbook install-elk.yml
ERROR! Syntax Error while loading YAML.
  did not find expected '-' indicator

The error appears to be in '/etc/ansible/files/install-elk.yml': line 10, column 3, but may
be elsewhere in the file depending on the exact syntax problem.

The offending line appears to be:


  - name: Install Docker module
  ^ here

root@40e19f1817ea:/etc/ansible/files# nano install-elk.yml
root@40e19f1817ea:/etc/ansible/files# ansible-playbook install-elk.yml
ERROR! Syntax Error while loading YAML.
  did not find expected '-' indicator

The error appears to be in '/etc/ansible/files/install-elk.yml': line 7, column 2, but may
be elsewhere in the file depending on the exact syntax problem.

The offending line appears to be:

  tasks:
 - name: Install docker.io
 ^ here

root@40e19f1817ea:/etc/ansible/files# nano install-elk.yml
root@40e19f1817ea:/etc/ansible/files# ansible-playbook install-elk.yml
ERROR! Syntax Error while loading YAML.
  did not find expected '-' indicator

The error appears to be in '/etc/ansible/files/install-elk.yml': line 7, column 2, but may
be elsewhere in the file depending on the exact syntax problem.

The offending line appears to be:

  tasks:
 -name: Install docker.io
 ^ here

root@40e19f1817ea:/etc/ansible/files# nano install-elk.yml
root@40e19f1817ea:/etc/ansible/files# ansible-playbook install-elk.yml
ERROR! Syntax Error while loading YAML.
  did not find expected '-' indicator

The error appears to be in '/etc/ansible/files/install-elk.yml': line 7, column 2, but may
be elsewhere in the file depending on the exact syntax problem.

The offending line appears to be:

  tasks:
 - name: Install docker.io
 ^ here

root@40e19f1817ea:/etc/ansible/files# nano install-elk.yml
root@40e19f1817ea:/etc/ansible/files# ansible-playbook install-elk.yml
ERROR! Syntax Error while loading YAML.
  did not find expected key

The error appears to be in '/etc/ansible/files/install-elk.yml': line 9, column 4, but may
be elsewhere in the file depending on the exact syntax problem.

The offending line appears to be:

  - name: Install docker.io
   apt:
   ^ here

root@40e19f1817ea:/etc/ansible/files# nano install-elk.yml
root@40e19f1817ea:/etc/ansible/files# ansible-playbook install-elk.yml
ERROR! Syntax Error while loading YAML.
  did not find expected key

The error appears to be in '/etc/ansible/files/install-elk.yml': line 16, column 4, but may
be elsewhere in the file depending on the exact syntax problem.

The offending line appears to be:

  - name: Increase virtual memory
   command: sysctl -w vm.max_map_count="262144"
   ^ here

root@40e19f1817ea:/etc/ansible/files# nano install-elk.yml
root@40e19f1817ea:/etc/ansible/files# ansible-playbook install-elk.yml
[WARNING]: Could not match supplied host pattern, ignoring: elk


PLAY [Configure Elk VM with Docker] ********************************************
skipping: no hosts matched

PLAY RECAP *********************************************************************

root@40e19f1817ea:/etc/ansible/files# nano install-elk.yml
root@40e19f1817ea:/etc/ansible/files# cd ..
root@40e19f1817ea:/etc/ansible# nano hosts
root@40e19f1817ea:/etc/ansible# cd files
root@40e19f1817ea:/etc/ansible/files# cat install-elk.yml
---
- name: Configure Elk VM with Docker
  hosts: elk
  remote_user: Gramirez
  become: true
  tasks:

  - name: Install docker.io
    apt:
     update_caatche: yes
     force_apt_get: yes
     name: docker.io
     state: present

  - name: Use more memory
    sysctl:
     name: vm.max_map_count
     value: "262144"
     state: present
     reload: yes

  - name: Increase virtual memory
    command: sysctl -w vm.max_map_count="262144"

  - name: Install python3-pip
    apt:
     force_apt_get: yes
     name: python3-pip
     state: present

  - name: Use more memory
    sysctl:
     name: vm.max_map_count
     value: "262144"
     state: present
     reload: yes

  - name: Install Docker module
    pip:
     name: docker
     state: present

  - name: download and launch a docker elk container
    docker_container:
     name: elk
     image: sebp/elk:761
     state: started
     restart_policy: always
     published_ports:
      - 5601:5601
      - 9200:9200
      - 5044:5044
root@40e19f1817ea:/etc/ansible/files# nano install-elk.yml
root@40e19f1817ea:/etc/ansible/files# ansible-playbook install-elk.yml
[WARNING]: Could not match supplied host pattern, ignoring: elk


PLAY [Configure Elk VM with Docker] ********************************************
skipping: no hosts matched

PLAY RECAP *********************************************************************

root@40e19f1817ea:/etc/ansible/files# nano install-elk.yml
root@40e19f1817ea:/etc/ansible/files# cd ..
root@40e19f1817ea:/etc/ansible# cd hosts
bash: cd: hosts: Not a directory
root@40e19f1817ea:/etc/ansible# nano host
root@40e19f1817ea:/etc/ansible# nano hosts
root@40e19f1817ea:/etc/ansible# cd files
root@40e19f1817ea:/etc/ansible/files# ansible-playbook install-elk.yml

PLAY [Configure Elk VM with Docker] ********************************************

TASK [Gathering Facts] *********************************************************
ok: [10.1.0.4]

TASK [Install docker.io] *******************************************************
fatal: [10.1.0.4]: FAILED! => {"changed": false, "msg": "Unsupported parameters for (apt) module: update_caatche Supported parameters include: allow_unauthenticated, autoclean, autoremove, cache_valid_time, deb, default_release, dpkg_options, force, force_apt_get, install_recommends, only_upgrade, package, policy_rc_d, purge, state, update_cache, upgrade"}

PLAY RECAP *********************************************************************
10.1.0.4                   : ok=1    changed=0    unreachable=0    failed=1    skipped=0    rescued=0    ignored=0

root@40e19f1817ea:/etc/ansible/files# nano install-elk.yml
root@40e19f1817ea:/etc/ansible/files# nano install-elk.yml
root@40e19f1817ea:/etc/ansible/files# ansible-playbook install-elk.yml

PLAY [Configure Elk VM with Docker] *************************************************************************************

TASK [Gathering Facts] **************************************************************************************************
ok: [10.1.0.4]

TASK [Install docker.io] ************************************************************************************************
changed: [10.1.0.4]

TASK [Use more memory] **************************************************************************************************
changed: [10.1.0.4]

TASK [Increase virtual memory] ******************************************************************************************
changed: [10.1.0.4]

TASK [Install python3-pip] **********************************************************************************************
changed: [10.1.0.4]

TASK [Install Docker module] ********************************************************************************************
changed: [10.1.0.4]

TASK [download and launch a docker elk container] ***********************************************************************
changed: [10.1.0.4]

PLAY RECAP **************************************************************************************************************
10.1.0.4                   : ok=7    changed=6    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0

root@40e19f1817ea:/etc/ansible/files# cd ~/
root@40e19f1817ea:~# cd .ssh
root@40e19f1817ea:~/.ssh# ssh Gramirez@10.1.0.4
Welcome to Ubuntu 18.04.5 LTS (GNU/Linux 5.4.0-1031-azure x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

  System information as of Fri Nov 13 03:27:55 UTC 2020

  System load:  1.37               Processes:              132
  Usage of /:   15.7% of 28.90GB   Users logged in:        0
  Memory usage: 70%                IP address for eth0:    10.1.0.4
  Swap usage:   0%                 IP address for docker0: 172.17.0.1

 * Introducing self-healing high availability clustering for MicroK8s!
   Super simple, hardened and opinionated Kubernetes for production.

     https://microk8s.io/high-availability

10 packages can be updated.
0 updates are security updates.

New release '20.04.1 LTS' available.
Run 'do-release-upgrade' to upgrade to it.


*** System restart required ***
Last login: Fri Nov 13 03:21:42 2020 from 10.0.0.4
Gramirez@ELK:~$ sudo docker ps
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS              PORTS                                                                              NAMES
cb00c074ab89        sebp/elk:761        "/usr/local/bin/star…"   3 minutes ago       Up 3 minutes        0.0.0.0:5044->5044/tcp, 0.0.0.0:5601->5601/tcp, 0.0.0.0:9200->9200/tcp, 9300/tcp   elk
Gramirez@ELK:~$ sudo container -a
sudo: container: command not found
Gramirez@ELK:~$ sudo container list -a
sudo: container: command not found
Gramirez@ELK:~$ sudo docker container list -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS              PORTS                                                                              NAMES
cb00c074ab89        sebp/elk:761        "/usr/local/bin/star…"   25 minutes ago      Up 25 minutes       0.0.0.0:5044->5044/tcp, 0.0.0.0:5601->5601/tcp, 0.0.0.0:9200->9200/tcp, 9300/tcp   elk
Gramirez@ELK:~$ sudo docker ps
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS              PORTS                                                                              NAMES
cb00c074ab89        sebp/elk:761        "/usr/local/bin/star…"   26 minutes ago      Up 26 minutes       0.0.0.0:5044->5044/tcp, 0.0.0.0:5601->5601/tcp, 0.0.0.0:9200->9200/tcp, 9300/tcp   elk
Gramirez@ELK:~$ sudo docker container list -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS              PORTS                                                                              NAMES
cb00c074ab89        sebp/elk:761        "/usr/local/bin/star…"   27 minutes ago      Up 26 minutes       0.0.0.0:5044->5044/tcp, 0.0.0.0:5601->5601/tcp, 0.0.0.0:9200->9200/tcp, 9300/tcp   elk
Gramirez@ELK:~$ exit
logout
Connection to 10.1.0.4 closed.
root@40e19f1817ea:~/.ssh# cd ~/
root@40e19f1817ea:~# cd /etc/ansible
root@40e19f1817ea:/etc/ansible# cd rolls
bash: cd: rolls: No such file or directory
root@40e19f1817ea:/etc/ansible# cd rols
bash: cd: rols: No such file or directory
root@40e19f1817ea:/etc/ansible# cd roles
root@40e19f1817ea:/etc/ansible/roles# nano filebeat-playbook.yml
root@40e19f1817ea:/etc/ansible/roles# ansible-playbook filebeat-playbook.yml
ERROR! Syntax Error while loading YAML.
  did not find expected '-' indicator

The error appears to be in '/etc/ansible/roles/filebeat-playbook.yml': line 7, column 3, but may
be elsewhere in the file depending on the exact syntax problem.

The offending line appears to be:


  - name: Download and Install Filebeat
  ^ here

root@40e19f1817ea:/etc/ansible/roles# nano filebeat-playbook.yml
root@40e19f1817ea:/etc/ansible/roles# ansible-playbook filebeat-playbook.yml

PLAY [Configure the filebeat] ****************************************************************************************************************

TASK [Gathering Facts] ***********************************************************************************************************************
The authenticity of host '10.0.0.8 (10.0.0.8)' can't be established.
ECDSA key fingerprint is SHA256:XjXTouoS7uY3Mu20/11c6LEDyhcHOeO+9J8Lw56DlwM.
Are you sure you want to continue connecting (yes/no)? The authenticity of host '10.0.0.10 (10.0.0.10)' can't be established.
ECDSA key fingerprint is SHA256:5cf84kYu/Xxext0rPevBicztXUtRiadNwnmmOu4k+Wg.
Are you sure you want to continue connecting (yes/no)? y
fatal: [10.0.0.10]: UNREACHABLE! => {"changed": false, "msg": "Failed to connect to the host via ssh: Host key verification failed.", "unreachable": true}
yes
Please type 'yes' or 'no': yes
fatal: [10.0.0.8]: UNREACHABLE! => {"changed": false, "msg": "Failed to connect to the host via ssh: Warning: Permanently added '10.0.0.8' (ECDSA) to the list of known hosts.\r\nGramirez@10.0.0.8: Permission denied (publickey).", "unreachable": true}

PLAY RECAP ***********************************************************************************************************************************
10.0.0.10                  : ok=0    changed=0    unreachable=1    failed=0    skipped=0    rescued=0    ignored=0
10.0.0.8                   : ok=0    changed=0    unreachable=1    failed=0    skipped=0    rescued=0    ignored=0

root@40e19f1817ea:/etc/ansible/roles# cd ~
root@40e19f1817ea:~# .ssh
bash: .ssh: command not found
root@40e19f1817ea:~# cd .ssh
root@40e19f1817ea:~/.ssh# ssh Gramirez@10.0.0.10
The authenticity of host '10.0.0.10 (10.0.0.10)' can't be established.
ECDSA key fingerprint is SHA256:5cf84kYu/Xxext0rPevBicztXUtRiadNwnmmOu4k+Wg.
Are you sure you want to continue connecting (yes/no)? yes
Warning: Permanently added '10.0.0.10' (ECDSA) to the list of known hosts.
Gramirez@10.0.0.10: Permission denied (publickey).
root@40e19f1817ea:~/.ssh# ls
id_rsa  id_rsa.pub  known_hosts
root@40e19f1817ea:~/.ssh# cat id_rsa.pub
ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDeE5HvyM4dww4+1bw+nd2GnjEpK1ueSHgZzYWfFeyhHEiSEscc1kElEf9ZvwQi+D5Yzso9zkVu31OxGX+vGzW/zkbZK+Q6tG5SHyXX1T+iJXsokciwmhijrp7ArDTXdC076m1JTjuC8NxIO3CvegZeiYI04u4nUxtr4ShZx6Vc7zFv4/Dtuco58MP2Zx69H+l7JUabED2M/eXYs37qzBwnRfnJCCoNXe6Si3F6fJrp05hK26Dk3XgIJ6pPLBHhBAJ1phpC3jkLoTqcJ4KvPr/+ImKLUdbEEzjCPXnzX8YtRB1SeZYoS497+8WminfdlknE2Bxp4jn+m42Gw1V6Cdxl root@40e19f1817ea
root@40e19f1817ea:~/.ssh# ssh Gramirez@10.0.0.10
Welcome to Ubuntu 18.04.5 LTS (GNU/Linux 5.4.0-1031-azure x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

  System information as of Fri Nov 13 04:09:35 UTC 2020

  System load:  0.06              Processes:           108
  Usage of /:   4.7% of 28.90GB   Users logged in:     0
  Memory usage: 21%               IP address for eth0: 10.0.0.10
  Swap usage:   0%

 * Introducing self-healing high availability clustering for MicroK8s!
   Super simple, hardened and opinionated Kubernetes for production.

     https://microk8s.io/high-availability

11 packages can be updated.
0 updates are security updates.



The programs included with the Ubuntu system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by
applicable law.

To run a command as administrator (user "root"), use "sudo <command>".
See "man sudo_root" for details.

Gramirez@web1:~$ exit
logout
Connection to 10.0.0.10 closed.
root@40e19f1817ea:~/.ssh# ssh Gramirez@10.0.0.8
Welcome to Ubuntu 18.04.5 LTS (GNU/Linux 5.4.0-1031-azure x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

  System information as of Fri Nov 13 04:09:51 UTC 2020

  System load:  0.0               Processes:           109
  Usage of /:   4.7% of 28.90GB   Users logged in:     0
  Memory usage: 21%               IP address for eth0: 10.0.0.8
  Swap usage:   0%

 * Introducing self-healing high availability clustering for MicroK8s!
   Super simple, hardened and opinionated Kubernetes for production.

     https://microk8s.io/high-availability

12 packages can be updated.
0 updates are security updates.


Last login: Fri Nov  6 01:50:15 2020 from 10.0.0.4
To run a command as administrator (user "root"), use "sudo <command>".
See "man sudo_root" for details.

Gramirez@web2:~$ exit
logout
Connection to 10.0.0.8 closed.
root@40e19f1817ea:~/.ssh# cd /etc/ansible
root@40e19f1817ea:/etc/ansible# ansible-playbook filebeat-playbook.yml
ERROR! the playbook: filebeat-playbook.yml could not be found
root@40e19f1817ea:/etc/ansible# cd file
bash: cd: file: No such file or directory
root@40e19f1817ea:/etc/ansible# cd roles
root@40e19f1817ea:/etc/ansible/roles# ansible-playbook filebeat-playbook.yml

PLAY [Configure the filebeat] **********************************************************************************************************************

TASK [Gathering Facts] *****************************************************************************************************************************
ok: [10.0.0.10]
ok: [10.0.0.8]

TASK [Download and Install Filebeat] ***************************************************************************************************************
[WARNING]: Consider using the get_url or uri module rather than running 'curl'.  If you need to use command because get_url or uri is insufficient
you can add 'warn: false' to this command task or set 'command_warnings=False' in ansible.cfg to get rid of this message.

changed: [10.0.0.10]
changed: [10.0.0.8]

TASK [Install] *************************************************************************************************************************************
changed: [10.0.0.8]
changed: [10.0.0.10]

TASK [drop in filebeat.yml] ************************************************************************************************************************
An exception occurred during task execution. To see the full traceback, use -vvv. The error was: If you are using a module and expect the file to exist on the remote, see the remote_src option
fatal: [10.0.0.8]: FAILED! => {"changed": false, "msg": "Could not find or access '/etc/ansible/files/filebeat-config.yml' on the Ansible Controller.\nIf you are using a module and expect the file to exist on the remote, see the remote_src option"}
An exception occurred during task execution. To see the full traceback, use -vvv. The error was: If you are using a module and expect the file to exist on the remote, see the remote_src option
fatal: [10.0.0.10]: FAILED! => {"changed": false, "msg": "Could not find or access '/etc/ansible/files/filebeat-config.yml' on the Ansible Controller.\nIf you are using a module and expect the file to exist on the remote, see the remote_src option"}

PLAY RECAP *****************************************************************************************************************************************
10.0.0.10                  : ok=3    changed=2    unreachable=0    failed=1    skipped=0    rescued=0    ignored=0
10.0.0.8                   : ok=3    changed=2    unreachable=0    failed=1    skipped=0    rescued=0    ignored=0

root@40e19f1817ea:/etc/ansible/roles# cd ..
root@40e19f1817ea:/etc/ansible# cd files
root@40e19f1817ea:/etc/ansible/files# ls
install-elk.yml




