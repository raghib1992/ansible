# ansible playbooks

## to get ansible doc
ansible-doc -l

## to run ansible command
ansible target -m ping -i inventory
ansible <host> -a <command>
ansible <host> -m <module>
   
## To run ansible playbook
ansible-playbook playbook.yml -i inventory.txt

# install roles from Ansible galaxy community
ansible-galaxy install <xxxxxxxx>
