Portainer
=========

This role will help you to deploy a Portainer server on standalone host.

Role Variables
--------------

The defaults/main.yml contains the defaults requiered  variables for the ports and volumes to deploy the Docker image. It also contains, the boolean variable "edge_agent" that will define if the installation should bind the TCP port used for the agent or not.

The vars/main.yml contains the specifics variables that will used whether if the host is a Windows instead of a Linux host, and the specifics value for the variable "ports" if we want to use EDGE agent later or not.

Example Playbook
----------------

For exemple, you can call the role with the variable edge_agent set to True, if you don't need to use the EDGE agent, you can set the variable to False or simply omit.

    - hosts: servers
      roles:
         - { role: portainer, edge_agent: True }
