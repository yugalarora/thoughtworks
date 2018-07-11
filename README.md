**Pre-requisites**

sudo pip install boto boto3 botocore ansible awscli

-------------------------------------------------------
The playbook has been broken into below parts:

***1) Environment provisioning:***
a) Create a VPC
b) Create a NAT Gateway
c) Attach EIP to NAT Gateway
d) Create 2 subnets (a Public/Weblayer and a Private/AppLayer)
e) Allow SSH from client to Server in Public subnet
(This server will act as a web server for our Application and Also a bastion to reach Private )
f) Allow SSH to servers in Private Subnet only from bastion
g) Allow/Restrict traffic between public and private subnet.

***2) Launch EC2 Servers:***
a) Launch a server in Public/AppLayer subnet, assign a public IP to it.
b) Launch a server in Private/Weblayer subnet

***3) Post provisioning setup:***
a) We'll propogate keys to bastion, so we can reach App server from there
b) Install required packages onto App and Web Server
