**Pre-requisites**

sudo pip install boto boto3 botocore ansible awscli

Note: you require an ubuntu or a linux system to run this playbook from

-------------------------------------------------------
The playbook has been broken into below parts:

***1) Environment provisioning:***

a) Create a VPC

b) Create a NAT Gateway

c) Attach EIP to NAT Gateway

d) Create 2 subnets (a Public/Weblayer and a Private/AppLayer)

e) Allow SSH from client to Server in Public subnet

**(This server will act as a web server for our Application and Also a bastion to reach servers inside AppSubnet)**

f) Allow SSH to servers in Private Subnet only from bastion

g) Allow/Restrict traffic between public and private subnet.

***2) Launch EC2 Servers:***

a) Launch a server in Public/AppLayer subnet, assign a public IP to it.

b) Launch a server in Private/Weblayer subnet

**Architectral view of Environment**
![alt text](aws.png "VPC architectral view")

***3) Deployment***

a) Will copy your private key into bastion/WebServer

b) Install Nginx as a service on WebServer

c) Install certificate and ssl key in nginx

d) Push configuration file inside nginx

e) Validate nginx configuration and start the service

f) Install Tomcat as a service on AppServer

g) Deploy sample.war available on 'https://tomcat.apache.org/tomcat-7.0-doc/appdev/sample/sample.war'
 in Webapps directory

h) Start tomcat service.

**Snapshot of Nginx running on https**
![alt text](Nginx.png "Nginx home page")
**Snapshot of Tomcat running on https**
![alt text](Tomcat.png "Tomcat sample webapp homepage")
