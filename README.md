# Ansible Collection - sivaramsk.arangodb

This collections support the below roles 
1. Arangodb Cluster installation using starter
2. Arangodb Cluster upgrade using stater
3. Arangodb Cluster uninstall (assumes installation using the above roles)
4. Arangodb Log collection (assumes installation using the above roles)

Each role is documented in its own page inside the roles folder.

Make sure the roles are placed on the roles_path. When checking out in a non_standard roles_path, use the ansible.cfg with roles_path set to the path where roles were downloaded and place the ansible.cfg in the same location as the playbook. Refer to the tests folder for sample.

```
[defaults]
inventory = ./hosts
roles_path = ../roles
```
