arangodb_cluster
=========

Install or upgrade Arangodb in cluster mode using arangodb starter. The role supports installing/upgrading agent, dbserver and coordinators in different servers and also in the same servers. Refer to the role variables on how to configure the role in different servers 

Requirements
------------

**Keep the 127.0.0.1 in the hosts.yaml as it is used to create credentials locally. Replace the other ip's appropriately**

The ansible-role is generic and should work on all the linux versions, it has been primarily tested with ubuntu 20.04

Role Variables
--------------

### Configuration Options for arangodb_starter role: 
__Take a look at the sample site.yml provided for configuring separate agents, dbservers and coordinator services__
```
---

arangodb_version: "3.8.2"
arangodb_authentication: false
arangodb_username: "root"
arangodb_password: ""
arangodb_starter_port: 8528
arangodb_agents:
  - 192.168.0.20
  - 192.168.0.21
  - 192.168.0.22
# DBServers and Coordinators IP to create TLS, if you are using seperate nodes for dbservers and coordinators.
# Refer: https://www.arangodb.com/docs/3.8/programs-starter-security.html#tls-server-certificates
arangodb_servers: 
  - 192.168.0.23
  - 192.168.0.24
  - 192.168.0.25
  - 192.168.0.26
  - 192.168.0.27
  - 192.168.0.28
  - 192.168.0.29
```
### Sample hosts file for installing agents, dbserver and coordinators seperately. 

```
127.0.0.1 ansible_connection=local

[agents]
192.168.0.20 ansible_user=vagrant 
192.168.0.21 ansible_user=vagrant
192.168.0.22 ansible_user=vagrant

[dbservers]
192.168.0.23 ansible_user=vagrant 
192.168.0.24 ansible_user=vagrant
192.168.0.25 ansible_user=vagrant

[coordinators]
192.168.0.26 ansible_user=vagrant 
192.168.0.27 ansible_user=vagrant
192.168.0.28 ansible_user=vagrant

Dependencies
------------

This role has dependecy on the role included in this collection
* arangodb_common_vars
* arangodb_credentials_setup

Example Playbook
----------------

Refer to the playbook in playbooks/install.yml and playbooks/upgrade.yml for an example.

License
-------

Apache License 2.0

Author Information
------------------

Sivaram Kannan (sivaramsk@gmail.com)
