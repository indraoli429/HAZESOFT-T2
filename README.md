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

Step 7: change the hosts ip address and remote_user in deploy_docker_ansible.yml file based on your VM
![image](https://github.com/indraoli429/HAZESOFT-T2/assets/42300489/ae507040-4b44-4b93-bf8f-0a2b5d192507)

Step 8: Run the following command to build the docker image
``` ansible
    ansible-playbook deploy_docker_ansible.yml -kK
```
where `-k` ask for the connection password and `-K` ask for priviledge password.
![image](https://github.com/indraoli429/HAZESOFT-T2/assets/42300489/ad67e3d1-ebdd-4520-94d0-6f394044b3b0)

Step 9: Go to your browser and type following url
```url
vm-ip-address:9000/site/
```
![image](https://github.com/indraoli429/HAZESOFT-T2/assets/42300489/bf71096e-cd66-40e9-8d01-e39ce5538889)
