## Ansible Project 1
Install Apache Web Server on two Vagrant VMs using Ansible

### Steps:
Part A - Setup Ansible Controller Machine
* 1 - Create Directory: mkdir ansible-controller
* 2 - Initialize Vagrant VM: vagrant init
* 3 - Update Vagrant file to set up ansible-controller VM: vi vagrantfile
* 4 - Start VM: vagrant up
* 5 - SSH VM: vagrant ssh
* 6 - Check ansible version: ansible --version

Part B - Setup SSH on Controller Machine
* 1 - Generate ssh keys on ansible-controller: ssh-keygen
* 2 - Copy public ssh key to shared folder <br>
cp /home/vagrant/.ssh/id_rsa.pub /vagrant
* 3 - Copy public ssh key to host folder <br>
copy id_rsa.pub /ansible-hosts

Part C - Setup Ansible Host Machines
* 1 - Create dir: mkdir ansible-hosts
* 2 - Initialize Vagrant VMs: vagrant init
* 3 - Update Vagrant file to set up two VMs for ansible-hosts
* 4 - Start VMs: vagrant up

Part D - Test SSH connection between Controller and Host Machines <br>
ansible -i hosts.vag all -m ping

Part E - Create Hosts and Playbook file on Controller Machine <br>
* vi hosts.vag
* vi ansible-install-apache-vagrant.yml

Part F - Run playbook on ansible-controller
* 1 - SSH to ansible-controller machine: vagrant ssh <br>
*	2 - Run playbook file <br>
ansible-playbook -i hosts playbook.yml (for all hosts) <br>
ansible-playbook -i hosts -l web playbook.yml (for specific host)

