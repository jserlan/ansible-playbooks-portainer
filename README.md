# ansible-seedbox-server

## Description :

This playbook will deploy a Portainer installation for Docker

### Requirements :

A Debian running machine (or an other Debian OS based).
A root user or an user with sudo privileges.

### Files and folders description

deploy-portainer.yml : list of role to deploy and the common variables. For instance, here you can edit you timezone or remove role from deployment.

roles/ : contains the roles used by the playbook deploy-portainer.yml

hosts/ : contains the hosts file used by the playbook. Here you can define the IP addresses you wan to deploy.

## Usage

### Clone the repository :

    git clone https://github.com/jserlan/ansible-playbooks-portainer.git

### Run the playbook :

    ansible-playbook --user $USERNAME --ask-pass --become --ask-become-pass -i hosts/dedibox deploy-portainer.yml

Playbook arguments :

    --ask-pass/-k : used if you didn't store your ssh key on the remote machine (optional)

    --become : used if your user need sudo to be granted privileges (optional)

    --ask-become-pass : used if your user need to set the password for each sudo command (optional)

    --inventory : set the host file that contains the seedbox group with the IP address(es) to deploy (mandatory)

    --user : set the remote user (mandatory)

## Configuration

The service will be available on http://\<your IP\>:9000/

## To do

Adding a SSL confugation with certbot and nginx
