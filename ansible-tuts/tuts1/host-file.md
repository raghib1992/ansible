# Host file
## by default- all host file anible take from 
```
/etc/ansible/hosts
[defaults]
inventory = /etc/ansible/hosts
```
## create custom host file, and to pass it to command
```
ansible all -m setup -i inventory-file
```