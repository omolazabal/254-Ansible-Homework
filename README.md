# Ansible-Playbooks

Configures a Debian and two CentOS servers using Ansible. Created for a class project for CS 254 - Software Development with Open Source Systems. You can find the documentation for Ansible playbooks [here](http://docs.ansible.com/ansible/latest/index.html). 

# Project Requirements
## Given
A VirtualBox appliance files. Contains
- tiny-debian8-32 (IP 10.0.5.101)
- tiny-centos7-32 (IP 10.0.5.102)
- tiny-centos7-32-b (IP 10.0.5.103)
- fed-lxde-32 (IP 10.0.5.100)

## Requirements
- Create an inventory file for the three managed machines.
- Create a playbook with roles to manage the basic setup of all three machines:
  - Create a new user named “manager”.
    - Make manager an admin with all sudo rights (add to wheel group or change the sudoers file).
    - Create and transfer ssh keys for manager to the server’s authorized keys.
  - Install the packages for mtr, tcpdump, nano.
  - Set the primary DNS server for the machines to 10.0.5.1, and the secondary to 209.244.0.3.
- Create a playbook and roles to set up iptables on each machine.
  - All servers should drop all UDP and TCP as the default policy.
  - Open up TCP ports 21, 22, 53, and 123, and UDP port 53 on all servers.
  - Open up TCP ports 25, 110, and 143 on tiny-centos7.
  - Open up TCP ports 80 and 443 on tiny-centos7-b.
