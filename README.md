Install ansistrano deploy and rollback roles:
ansible-galaxy install -r ansible/requirements.yml

Edit variables:
ansible-vault edit ansible/environments/prod/vars/deploy_vault.yml (vault_pass is hamid)

Deploy symfony project:
ansible-playbook -i ansible/environments/prod/hosts.ini ansible/rollback/gut-web.yml  --ask-vault-pass

Rollback symfony project:
ansible-playbook -i ansible/environments/prod/hosts.ini ansible/deploy/gut-web.yml  --ask-vault-pass