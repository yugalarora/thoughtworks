Role Name
=========

Role does below:
a) Copy **id_rsa** private key onto server
b) Install Nginx version 1.12
c) Place ssl certificate and key on server
d) Places default.conf inside nginx /etc/nginx/conf.d/ directory

Requirements
------------

Internet access
Requires become: yes ! sudo access on server

Role Variables
--------------

Variables are sourced from vars/main.yml file (Refer comments in file for more details).

Dependencies
------------

##id_rsa##
should be private key for public key, used to launch ec2-instances in provisioning role.

Example Playbook
----------------

Including an example of how to use the role:

    - hosts: local
      roles:
         - { role: nginx }
