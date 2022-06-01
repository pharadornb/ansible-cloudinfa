# Role Challenge
1) Create a web-server role that installs apache (httpd) and starts the service.
2) Create a database role that installs mariadb by default but we want to install MySQL and start the service
3) The DB MUST Start before the web server

## Step of work role Challenge
- create folder role
- access to folder cmd: 
```
ansible-galaxy init web
```
```
ansible-galaxy init db
```