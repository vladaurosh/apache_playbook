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

This playbook can pass 2 optional variables:
- rpm_version
- roolback

"rollback" variable is added to support rpm downgrade (rollback). If variable is not passed, default is no which means downgrade is not allowed.

"rpm_version" variable is added to support installation of specific httpd version. If variable is not passed, then latest available httpd version will be installed. If we want to install specific httpd version we should pass for example:
rpm_version=-2.4.6-88.el7.centos.x86_64

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
