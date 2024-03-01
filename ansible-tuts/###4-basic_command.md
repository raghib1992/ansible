ansible <host> -m <module> -i <inventory-file>
ansible-playbook <playbook file> -i <inventory file>
ansible-inventory --host <host name>
ansible-playbook <playbook> --extra-vars webserver=nginx
## Command to create role structure
```sh
ansible-galaxy init <role name>
```