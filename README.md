Ansible-Learning
================

The purpose of this repository is to provide direction and examples to assist with Ansible learning.

### Getting Started

You should consider to configure your local dev environment in the same way that you would for a more formal environment.

```bash
# phython 2.7 assumed to be installed along with python-pip
python --version
# install via pip
pip install ansible
```

### Reading Resources

Before you begin you will want to read up on [YAML syntax](http://docs.ansible.com/ansible/YAMLSyntax.html).

There are a lot of resources online. I primarily use the [ansible docs](http://docs.ansible.com/ansible/index.html) to reference ansible. It lists infomration on [playbooks](http://docs.ansible.com/ansible/playbooks.html) and [modules](http://docs.ansible.com/ansible/modules_by_category.html).

There are also [example playbooks](https://github.com/ansible/ansible-examples) which provides information on common setup. 

### Inventory

Your inventory defines the hosts, servers, services that you want to interact with. [ansible inventory](http://docs.ansible.com/ansible/intro_inventory.html) provides information on how to manage and utlise an inventory.

You will need to start with defining where you want to manage your inventory.

```ansible.cfg
# ansible.cfg
[defaults]
hostfile = ./inventory
```

If `hostfile` points to a directory, any scripts within will be executed and then any static inventory files will be evaluated.

#### Dynamic Inventory

[Dynamic inventory](http://docs.ansible.com/ansible/intro_dynamic_inventory.html) allows you to generate an inventory via a script. For implementations of dynamic inventory across various providers see [contrib dynamic inventory](https://github.com/ansible/ansible/tree/devel/contrib/inventory)

Before you being you should consider how you want to manage resources. If you're using cloud resources you should utilise a dynamic inventory so you don't need to manage your inventory directly.

### Modules

You aren't limited to modules bundled in with ansible but they do provide you with 99% of the capability that you will likely require.

#### Core Modules

There isn't a need to go through all the modules. See the [modules list](http://docs.ansible.com/ansible/modules_by_category.html) for more information.

Some of the more go-to modules are

- [file module](http://docs.ansible.com/ansible/file_module.html) creating files/directories, setting permissions or creating symlinks.
- [sync module](http://docs.ansible.com/ansible/synchronize_module.html) it's rsync in a module
- [copy module](http://docs.ansible.com/ansible/copy_module.html) useful for copying a file or folder to/from target host
- [template module](http://docs.ansible.com/ansible/template_module.html) configuration files often need to be modified for the target host. this can be done programatically using templates.
- [shell module](http://docs.ansible.com/ansible/shell_module.html) when you've tried everything else and can't find a solution, use shell

#### External Libraries

Utilising external modules is fairly simple to set up.

Using [ansible-xml module](https://github.com/cmprescott/ansible-xml) as an example

```bash
mkdir library
cd library
git clone https://github.com/cmprescott/ansible-xml.git
```

update ansible.cfg to utlise module
```ansible.cfg
# ansible.cfg
[defaults]
library=./library
```
