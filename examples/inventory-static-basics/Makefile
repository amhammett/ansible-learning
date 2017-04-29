.PHONY: test

test: | db-deploy-list db-deploy web-deploy-list web-deploy

db-deploy:
	ansible-playbook database-deploy.yml

db-deploy-list:
	ansible-playbook database-deploy.yml --list-hosts

web-deploy:
	ansible-playbook website-deploy.yml

web-deploy-list:
	ansible-playbook website-deploy.yml --list-hosts
