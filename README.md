# ansible-seedbox-server

## Description :

This playbook will deploy a Portainer installation for Docker

### Requirements :

A Linux machine and a root user or at least an user with sudo privileges.

### Files and folders description

deploy-portainer.yml : list of role to deploy and the common variables. For instance, here you can edit you timezone or remove role from deployment.

ansible.cfg : contains my custom parameters for ansible.

roles/ : contains the roles used by the playbook deploy-portainer.yml

hosts/ : contains the hosts file used by the playbook. Here you can define the IP addresses that you wan to deploy.

## Usage

### Clone the repository :

    git clone https://github.com/jserlan/ansible-playbooks-portainer.git

### Run the playbook :

    ansible-playbook -k -b -K -u $USERNAME -i hosts/default deploy-portainer.yml

Playbook arguments :

    -k (or --ask-pass) : used if you didn't store your ssh key on the remote machine (optional)

    -b (or --become) : used if your user need sudo to be granted privileges (optional)

    -K (or --ask-become-pass) : used if your user need to set the password for each sudo command (optional)

    -i (or --inventory) : set the host file that contains the seedbox group with the IP address(es) to deploy (mandatory)

    -u (or --user) : set the remote user (mandatory)

## Configuration

The service will be available on the URL `http://<your IP>:9000/`

## To do

- Adding a SSL confugation with certbot and nginx
- Adding UFW and fail2ban roles
