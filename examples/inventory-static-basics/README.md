inventory | static basics
=========================

There are times where it's more convenient to start with a static inventory.

A `Makefile` has been created to simplify the running of playbooks. 

### Defining an inventory

First you will need to tell ansible where it will find your inventory.

```ansible.cfg
# ./ansible.cfg
[defaults]
hostfile = ./inventory
```

This tells ansible to look in the inventory directory. Ansible will execute any scripts
and read any non-executable files.

In this example we will specify two host groups, `db` and `web`.

### Referencing your inventory

This example includes two hosts groups found within `./inventory/hosts`, `web` and `db`. 
Playbooks have been created to reference host groups within the inventory.

```ansible
# website-deploy.yml
- hosts: web
```

A playbook specifies the hosts/servers/services that it will target. In this example the
two playbooks will run against all hosts within `db` and `web`.
