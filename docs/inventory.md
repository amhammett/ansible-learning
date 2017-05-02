### Inventory

Your inventory defines the hosts, servers, services that you want to
interact with. [ansible inventory](http://docs.ansible.com/ansible/intro_inventory.html)
provides information on how to manage and utlise an inventory.

You will need to start with defining where you want to manage your inventory.

```ansible.cfg
# ansible.cfg
[defaults]
hostfile = ./inventory
```

If `hostfile` points to a directory, any scripts within will be executed and
then any static inventory files will be evaluated.

#### Dynamic Inventory

[Dynamic inventory](http://docs.ansible.com/ansible/intro_dynamic_inventory.html)
allows you to generate an inventory via a script. For implementations of dynamic
inventory across various providers see [contrib dynamic inventory](https://github.com/ansible/ansible/tree/devel/contrib/inventory)

Before you being you should consider how you want to manage resources. If you're
using cloud resources you should utilise a dynamic inventory so you don't need to
manage your inventory directly.
