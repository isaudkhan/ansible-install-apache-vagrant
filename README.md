# Ansible Project 1
Install Apache Web Server on two Vagrant VMs using Ansible

### Steps:
1. Setup Ansible Controller Machine
    - Create Directory: mkdir ansible-controller
    - Initialize Vagrant VM: vagrant init
    - Update Vagrant file to set up ansible-controller VM: vi vagrantfile
    - Start VM: vagrant up
    - SSH VM: vagrant ssh
    - Check ansible version: ansible --version

2. Setup SSH on Controller Machine
    - Generate ssh keys on ansible-controller: ssh-keygen
    - Copy public ssh key to shared folder <br>
``
cp /home/vagrant/.ssh/id_rsa.pub /vagrant
``
    - Copy public ssh key to host folder <br>
``
copy id_rsa.pub /ansible-hosts
``

3. Setup Ansible Host Machines
    - Create dir: mkdir ansible-hosts
    - Initialize Vagrant VMs: vagrant init
    - Update Vagrant file to set up two VMs for ansible-hosts
    - Start VMs: vagrant up

4. Test SSH connection between Controller and Host Machines <br>
``
ansible -i hosts.vag all -m ping
``

5. Create Hosts and Playbook file on Controller Machine <br>
```
vi hosts.vag
vi ansible-install-apache-vagrant.yml
```
6. Run playbook on ansible-controller
    - SSH to ansible-controller machine: vagrant ssh <br>
    - Run playbook file ( -l : for specific host ) <br>
```
ansible-playbook -i hosts playbook.yml
ansible-playbook -i hosts -l web playbook.yml
```
