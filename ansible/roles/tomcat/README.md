tomcat
=========

Role does following:
a) Install tomcat
b) Download sample.war from tomcat offical websites and deploys it

Requirements
------------

Internet access on server and sudo privelidges

Role Variables
--------------

None

Dependencies
------------

None

Example Playbook
----------------

Including an example of how to use the role:

    - hosts: Appservers
      roles:
         - { role: tomcat }
