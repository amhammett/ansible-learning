Ansible-Learning
================

The purpose of this repository is to provide direction and examples to assist
with Ansible learning.

### Reading Resources

Before you begin you will want to read up on [YAML syntax](http://docs.ansible.com/ansible/YAMLSyntax.html).

There are a lot of resources online. I primarily use the [ansible docs](http://docs.ansible.com/ansible/index.html)
to reference ansible. It lists information on [playbooks](http://docs.ansible.com/ansible/playbooks.html)
and [modules](http://docs.ansible.com/ansible/modules_by_category.html).

There are also [example playbooks](https://github.com/ansible/ansible-examples)
which provides information on common setup. 

### Wiki Pages

Describing various topics

| Topics | Description |
| ------ | ----------- |
| [Getting Started](wiki/getting-started.md) | How to configure your environment to use ansible
| [Inventory](wiki/inventory.md) | Static and dynamic inventories |
| [modules and libraries](wiki/modules.md) | Using core and community modules |


### Examples

A few examples put together to show implementation options or comparisons.

| Examples | Description |
| -------- | ----------- |
| [files and folders](examples/files-and-folders) | A comparison between the shell and file module for folder structures |
| [inventory static basics](examples/inventory-static-basics) | Introduction to static inventory |
| [ansible-vault](examples/ansible-vault) | Managing secrets with ansible-vault |
