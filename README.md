# Ansible Automation Cloud Infrastructure

## Important commands
### `basic ansible`
- Ping the server for your service on cloud(aws)
```
ansible web -i aws.ini -m ping
```
- ssh for .pem key by instance on cloud(aws)
```
chmod 400 <name_key>.pem
```
- windows server on cloud(aws)
```
ansible windows -i win_server.yaml -m win_whoami
```

-----
## Role Challenge
1) Create a web-server role that installs apache (httpd) and starts the service.
2) Create a database role that installs mariadb by default but we want to install MySQL and start the service
3) The DB MUST Start before the web server

### Step of work role Challenge
- create folder role
- access to folder cmd: 
```
ansible-galaxy init web
```
```
ansible-galaxy init db
```

---
## Inventory Challenge
1) Create 3 Individual Hosts:
        ⁃	mail.mycorp.local
        ⁃	smtp.mycorp.local
        ⁃	auth.mycorp.local
2) Group the Domain Controllers:
    ⁃	dc01.mycorp.local
    ⁃	dc02.mycorp.local
3) Group the London App servers:
    ⁃	app01.ldn.mycorp.local
    ⁃	app02.lnd.mycorp.local
4) Group the Texas App Servers:
    ⁃	app03.tx.mycorp.local
    ⁃	app04.tx.mycorp.local
5) Group the London and Texas servers in a single group called: itlappsrv

---
## Web-server challenge
1) update all packages on the server
2) install Apache (httpd)
3) Create an HTML page using this command: echo "Hello From The Ansible Challenge" > /var/www/html/index.html
4) Reload Apache
5) Get the public IP address of the server

---
## Resources For interresting
### `- ansible-galaxy`
https://galaxy.ansible.com/home
https://github.com/companieshouse/ansible-role-apache
https://docs.ansible.com/ansible/latest/user_guide/playbooks_reuse_roles.html
### `- dynamic inventory`
https://docs.ansible.com/ansible/latest/user_guide/intro_dynamic_inventory.html
https://raw.githubusercontent.com/ansible/ansible/stable-1.9/plugins/inventory/ec2.py
https://raw.githubusercontent.com/ansible/ansible/stable-1.9/plugins/inventory/ec2.ini
### `- ansible-windows-aws-server`
https://docs.ansible.com/ansible/latest/user_guide/windows_setup.html


*/ Role /*
create --> ansible-galaxy init apache
ansible-playbook -i aws.ini roles/playbook.yaml
ansible-galaxy install --roles-path . -r requirements.yaml
ansible-galaxy collection install -p . -r requirements.yaml
ansible-playbook -i aws.ini -e "basic_var=CLI" variables/var_role.yaml
ansible-playbook -i aws.ini roles/playbook.yaml

*/ Var cmd run /*
ansible-playbook basic.yaml
ansible-playbook -e "@var.yaml" var_file_demo.yaml --> file outside inherit file
ansible-playbook -i aws.ini variables/multi.yaml
ansible-playbook -e "basic_var=CLI" cli.yaml
ansible-playbook -i aws.ini playbook.yaml
ansible-playbook -i aws.ini playbooks/service.yaml