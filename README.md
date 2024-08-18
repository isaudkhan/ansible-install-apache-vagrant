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
* 3 - Copy public ssh key to host folder
copy id_rsa.pub /ansible-hosts

Part C - Setup Ansible Host Machines
* 1 - Create dir: mkdir ansible-hosts
* 2 - Initialize Vagrant VMs: vagrant init
* 3 - Update Vagrant file to set up two VMs for ansible-hosts
* 4 - Start VMs: vagrant up

Part D - Test SSH connection between Controller and Host Machines
ansible all -m ping -i hosts

