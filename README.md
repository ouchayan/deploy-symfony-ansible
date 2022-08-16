- Install ansible :<br>
sudo apt install ansible

- Clone the project :<br>
https://github.com/ouchayan/deploy-symfony-ansible.git

- Install ansistrano deploy and rollback roles: <br>
ansible-galaxy install -r ansible/requirements.yml

- Edit variables:<br>
ansible-vault edit ansible/environments/prod/vars/deploy_vault.yml (vault_pass is hamid)

- Deploy symfony project:<br>
ansible-playbook -i ansible/environments/prod/hosts.ini ansible/rollback/gut-web.yml  --ask-vault-pass

- Rollback symfony project:<br>
ansible-playbook -i ansible/environments/prod/hosts.ini ansible/deploy/gut-web.yml  --ask-vault-pass
