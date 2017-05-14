repo_name      = foo
vault_password = --vault-password-file ../../.secrets/$(repo_name).vault
ansible_cmd    = ansible-playbook $(vault_password) -i localhost,

edit-secrets:
	ansible-vault $(vault_password) edit vars/secrets.yml

foo-secrets:
	$(ansible_cmd) foo-secrets.yml
