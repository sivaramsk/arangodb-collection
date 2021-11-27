arangodb_log_collect
=========

Collect logs from the arangodb components agents, dbservers and coordinators and bring it to the controller node. 

Requirements
------------

The role assumes the arangodb was installed using the arangodb_starter_install role.

Role Variables
--------------

`no_of_lines` - default is 10000, a value of all will collect all the logs lines for the service.


Dependencies
------------

arangodb_common_vars

Example Playbook
----------------

Refer to the playbook in playbooks/logcollect.yaml for an example.

License
-------

Apache License 2.0

Author Information
------------------

Sivaram Kannan (sivaramsk@gmail.com)
