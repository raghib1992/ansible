# Inventory File
```
alias      fqdn                   connection-type         port          username                       passowrd
web ansible_host=192.168.56.3 ansible_connection=ssh ansible_port=22 ansible_user=kubeworker01 ansible_ssh_pass=s3cret#123
localhost ansible_connection=localhostwhoami
node01 ansible_host=kubenode01
node02 ansible_host=kubenode02 ansible_ssh_private_key_file=./node04.pem
```

**************************************************
ec2 ansible_host=13.232.234.197 webserver=tomcat ansible_connection=ssh ansible_user=ansiuser ansible_port=22 ansible_priva># ssh -i ../ansiuser ansiuser@locahost -p 2525
container ansible_host=localhost ansible_connection=ssh ansible_port=2525 ansible_user=ansiuser ansible_private_key_file=..>#################

[dev]
dev1 ansible_host=3.110.166.15 ansible_connection=ssh ansible_user=ec2-user ansible_private_key_file=mumbai-key.pem

[prod]
prod1 ansible_host=3.110.155.19 
prod2 ansible_host=43.204.140.121

[prod:vars]
ansible_connection=ssh
ansible_user=ec2-user
ansible_private_key_file=mumbai-key.pem



define host_vars and groups_vars

${ROOT_DIR_INV}/host_vars/<HOSTNAME>.yaml

${ROOT_DIR_INV}/host_vars/<HOSTNAME>/*.yaml

${ROOT_DIR_INV}/group_vars/<GROUP_NAME>.yaml

${ROOT_DIR_INV}/group_vars/<GROUP_NAME>/*.yaml


###############################
hosts.ini
web
192.168.0.1

[db]
db1.mydomain.local
db2.mydomain.local
db3.mydomain.local

[web]
web1.mydomain.local
web2.mydomain.local
web3.mydomain.local

# Gropu of groups
[prod:children]
db
web
####################################
hosts.yaml

all:
    hosts:
        web.mydomain.com:
        192.168.0.1
    customer1:
        children:
            db:
                db1.mydomain.local:
                db2.mydomain.local:
                db3.mydomain.local:
            web:
                web1.mydomain.local:
                web2.mydomain.local:
                web3.mydomain.local:


