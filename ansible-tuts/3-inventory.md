Default inventory file located at 
/etc/ansible/hosts
# Invenroty format
1. ini
2. yaml
# Inventory File
|  alias | fqdn   | connection-type  | port  | username  | password  |
|---|---|---|---|---|---|
|  web | ansible_host=192.168.56.3 |  ansible_connection=ssh | ansible_port=22  | ansible_user=kubeworker01   | ansible_ssh_pass=s3cret#123  |
|  localhost |   |  ansible_connection=localhostwhoami |   |   | ansible_ssh_private_key_file=./node04.pem  |


#### There was many way to define inventory file
1.inventory file
```
[dev]
dev1 ansible_host=3.110.166.15 ansible_connection=ssh ansible_user=ec2-user ansible_private_key_file=mumbai-key.pem

[prod]
prod1 ansible_host=3.110.155.19 ansible_connection=winrm
prod2 ansible_host=43.204.140.121 ansible_connection=winrm

[prod:vars]
ansible_connection=ssh
ansible_user=ec2-user
ansible_private_key_file=mumbai-key.pem
```
2. inventory file
```
server1.company.com
server2.company.com
server3.company.com
server4.company.com
```

#### hosts.ini
```
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
```

#### hosts.yaml
```
all:
    children:
        hosts:
            web.mydomain.com:
            192.168.0.1:
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
```


### define host_vars and groups_vars
```
${ROOT_DIR_INV}/host_vars/<HOSTNAME>.yaml

${ROOT_DIR_INV}/host_vars/<HOSTNAME>/*.yaml

${ROOT_DIR_INV}/group_vars/<GROUP_NAME>.yaml

${ROOT_DIR_INV}/group_vars/<GROUP_NAME>/*.yaml
```