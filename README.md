# HAZESOFT-T2
AUtomate the [task 1](https://github.com/indraoli429/HAZESOFT-T1.git) using ansibel

# 
Step 1: Install ansible on your machine
```bash
sudo apt update
sudo apt install ansible

#verify ansible
ansible --version
```
Step 2: Prepare VM for testing
- Install any type 2 hypervisor
- Create VM and change network adapter into bridge mode
- Setup static ip (use host machine network)

Step 3: Generate ssh-keygen on host machine and copy to newly created VM
```bash
ssh-keygen
ssh-copy-id -i /path/to/ssh-public-key.pub user@host-ip
```
Step 4: Create a host/inventory for ansible
- create hosts file inside /etc/ansible
- write vm ip address in hosts file (see hosts_sample)

Step 5: clone the given github repo
```git
git clone https://github.com/indraoli429/HAZESOFT-T2.git
```

Step 6: Nevigate to the repo

Step 7: Run the following command to build the docker image
``` ansible
    ansible-playbook deploy_docker_ansible.yml -kK
```
where `-k` ask for the connection password and `-K` ask for priviledge password.

Step 8: Go to your browser and type following url
```url
vm-ip-address:9000/site/
```