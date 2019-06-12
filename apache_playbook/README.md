Playbook Name
=========

This ansible playbook will install httpd (apache) web server on multiple server using using ansible role available here:
https://github.com/vladaurosh/ansible-role/tree/master/deploy_httpd_app

Requirements
------------

No pre-requisites needed.

Dependencies
------------

No dependencies.

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
