1. Variables i command line
ansible-playbook playbook.yaml --extra-vars webserver=nginx

2. Variable define in play
vars:
    webserver: nginx

vars_file:
    - myvars.yaml

3. Variable define in Inventory
ec2 ansible_host=192.168.1.1 ansible_connectioon=ssh webserver=nginx ansible_port=22

vars/users.yaml

assignment_user_name: ahmed
assignment_user_id: 4000
assignment_group: developers


inventory_hostname  string
hostvars            key-value pair
group_names         Array
groups              key-value pair


++++++++++++++++++++++++++++++