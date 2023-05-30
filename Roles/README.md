# Install a new role
ansible-galaxy install raghib.webpage


# Install a new role from requirement.yaml 
ansible-galaxy install -r ./requirement.yaml

# Create new role from scratch
ansible-galaxy init my-role


# to get help
ansible-galaxy --help


#################
# tell ansible where to download roles
ansible.cfg
[default]
roles_path = ./roles

# install roles
ansible-galaxy install -r ./requirement.yaml


# Import with module task
tasks:
    - import_role:
        name: adihfsdh
        vars: {var1:val1,....}

# Import at play level
hosts:
roles:
- name: adihfsdh
  var1: val1