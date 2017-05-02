.PHONY: test

ansible_cmd = ansible-playbook -i localhost,


test: | folder-structure-shell folder-structure-file

folder-structure-shell:
	$(ansible_cmd) folder-structure-shell.yml

folder-structure-file:
	$(ansible_cmd) folder-structure-file.yml
