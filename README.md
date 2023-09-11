# ansible
## Install ansible
```sh
sudo update 
sudo apt install -y ansible
```
### Install using pip
```sh
# check for pip
python3 -m pip -V

# if pip is not available
curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py
python3 get-pip.py --user

# Installing Ansible
python3 -m pip install --user ansible

# check anisble version
ansible --version
```

## Agent less configuration tool, no need to install any software at target tool.
## Ansible locate its host details in hosts file, by default it looks at:
```
/etc/ansible/hosts
```
### by default this disable host_key_chekcing=False (unable to ssh a new host)
### /etc/ansible/ansible.cfg
### Uncomment it
```
vi /etc/ansible/ansible.cfg
host_key_checking= False
```

## to learn more about ansible module 
```
ansible-doc -l
```

## Command
```sh
ansible <host alias> -m ping -i inventory
ansible all -a <command>
ansible <host-alias> -a <command> -i inventory
ansible <host-alias> -m <module> -i inventory
ansible-playbook <playbook name> -i <inventory file name>
```
## Command to create role structure
```sh
ansible-galaxy init <role name>
```
## to search role form ansible-galaxy
### use ui or
### cli
```sh
ansible-galaxy search <role-name>
ansible-galaxy install <role-name>
ansible-galaxy install <role-name> -p ./roles
ansible-galaxy list
ansible-config dump | grep ROLE
```
#### Default location where ansible search for roles- /etc/ansible/roles
*********************************************************************************
# Separate file
## Host variable
### create folder at same level of playbook
### name host_vars
#### Create yaml file with name of the server alias
#### web.yaml
```
ansible_host: 192.168.56.3
ansible_ssh_private_key_file: ../node01.pem
```

## group variable
### create folder at same level of playbook
### name group_vars
#### Create yaml file with name of the server alias
#### web.yaml
