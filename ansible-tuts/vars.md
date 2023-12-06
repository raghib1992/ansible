## Pass variable to plya book in following ways
1. Variables in command line
```sh
ansible-playbook playbook.yaml --extra-vars webserver=nginx
```
2. Variable define in play
```yaml
# Define variable in playbook
vars:
    webserver: nginx
# Refer var file in playbook
vars_file:
    - myvars.yaml
```
```yaml
#vars/users.yaml
assignment_user_name: ahmed
assignment_user_id: 4000
assignment_group: developers
```

3. Variable define in Inventory
```t
ec2 ansible_host=192.168.1.1 ansible_connectioon=ssh webserver=nginx ansible_port=22
```

4. Define vaiable in varsfile



inventory_hostname  string
hostvars            key-value pair
group_names         Array
groups              key-value pair


++++++++++++++++++++++++++++++