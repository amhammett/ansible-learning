### Modules

You aren't limited to modules bundled in with ansible but they do provide
you with 99% of the capability that you will likely require.

#### Core Modules

There isn't a need to go through all the modules. See the [modules list](http://docs.ansible.com/ansible/modules_by_category.html)
for more information.

Some of the more go-to modules are

- [file module](http://docs.ansible.com/ansible/file_module.html) creating
files/directories, setting permissions or creating symlinks.
- [sync module](http://docs.ansible.com/ansible/synchronize_module.html)
it's rsync in a module
- [copy module](http://docs.ansible.com/ansible/copy_module.html) useful
for copying a file or folder to/from target host
- [template module](http://docs.ansible.com/ansible/template_module.html)
configuration files often need to be modified for the target host. this 
can be done programatically using templates.
- [shell module](http://docs.ansible.com/ansible/shell_module.html) when
you've tried everything else and can't find a solution, use shell

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
