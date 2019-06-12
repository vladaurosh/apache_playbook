Playbook Name
=========

This ansible playbook will install httpd (apache) web server on multiple server using using ansible role available here:
https://github.com/vladaurosh/ansible-role/tree/master/deploy_httpd_app

To support rolling updates this playbook will be executed in batches of 20% of servers. 

Requirements
------------

No pre-requisites needed.

Dependencies
------------

No dependencies.

Role Variables
--------------

This playbook can pass 3 optional variables:
- rpm_version
- roolback
- server_percent

"rollback" variable is added to support rpm downgrade (rollback). If variable is not passed, default is no which means downgrade is not allowed.

"rpm_version" variable is added to support installation of specific httpd version. If variable is not passed, then latest available httpd version will be installed. If we want to install specific httpd version we should pass for example:
rpm_version=-2.4.6-88.el7.centos.x86_64

"server_percent" is added to support rolling updates so if we want to execute playbook on for example 20% of all servers we can pass 20:
--extra-vars "server_percent=20"
If we want to process all servers in parallel we can pass 100 or just skip this variable (default is 100% of servers).                             

Example Playbook
----------------

Including an example of how to use this playbook:                       
 \# ansible-playbook apache.yml -i hosts --extra-vars "rpm_version=-2.4.6-88.el7.centos.x86_64" --extra-vars "roolback=yes"

License
-------

GPL

Author Information
------------------

Vlad U
