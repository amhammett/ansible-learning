modules | files and folders
===========================

If you're working from scripts and porting it to ansible it can be easy to
take over line by line or script by script.

### files and folders via the shell module

```ansible
make folder-structure-shell
```

if your script looked something like

```shell
    workspace:   "{{playbook_dir}}/tmp/shell"
    test_file:   "test.txt"
    test_string: "this is not a test"

# create workspace
mkdir -p ./tmp/shell

# touch file
touch ./tmp/shell/file.touch

# update file contents
echo "this is not a test" > ./tmp/shell/test.txt

# read file value
file_contents = $(cat ./tmp/shell/test.txt)

# display contents
echo test.txt contains '$(file_contents)'
```

You could take line by line and create in ansible. It would work as you would
expect but may not get all the benefits of ansible, such as knowing when a
change has taken place or when the state is already in the expected state.

The shell module always considers state to be changed unless you overwrite.

### files and folders via the file module

```ansible
make folder-structure-file
```

This playbook aims to get the same state but does so using the ansible file
and copy modules.

If you run the playbook more than once you will see that the changed status
only shows when a change takes place
