.PHONY: test

repo_name      = ansible-learning
vault_password = --vault-password-file ./.secrets/$(repo_name).vault
ansible_cmd    = ansible-playbook $(vault_password) -i localhost,

test: | generate-vault-password single-vault multiple-vaults

edit-secrets:
	ansible-vault $(vault_password) edit vars/secrets.yml

generate-vault-password:
	$(ansible_cmd) generate-vault-password.yml

single-vault:
	$(ansible_cmd) single-vault.yml

multiple-vaults:
	$(ansible_cmd) multiple-vaults.yml
	@echo view foo\'s secrets
	make -C repo/foo/ foo-secrets
	@echo view bars\'s secrets
	make -C repo/bar bar-secrets
