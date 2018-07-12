provisioning
=========

This role will:
a) Create a VPC
b) Create a Public Subnet
c) Create a Private Subnet
d) Create a NAT Gateway, attach an EIP to it
e) Launch EC2 instances in above sunets
f) Assign Public IP to EC2 instances in Public Subnet

Requirements
------------

Internet access
Role requires below libraries to be present on host from where it is being run:
*python
boto
botocore
boto3
awscli*

##id_rsa.pub##

Key passed as pem keypair to AWS, corresponding private key will need to be passed to bastion after launching in nginx role.

Role Variables
--------------

Role uses variables that are sourced from vars/main.yml (Refer comments in file for more details)

Dependencies
------------

None, as of now.

Example Playbook
----------------

Including an example of how to use role:

    - hosts: local
      roles:
         - { role: provisioning }
