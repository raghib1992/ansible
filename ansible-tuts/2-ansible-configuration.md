create default configuration file at
/etc/ansible/ansible.cfg

to override default config file, create a ansible.cfg file in local directory of playbook.


To define particular ansible.cfg file to use mention the file
ANSIBLE_CONFIG=/otp/ansible-web.cfg ansible-playbook playbook.yaml

Priority wise ansble.cfg
1. ANSIBLE_CONFIG=/otp/ansible-web.cfg ansible-playbook playbook.yaml
2. ansible.cfg file local dir
3. in home directory .ansible.cfg
4. default location /etc/ansible/ansible.cfg

We can also update single parameter in ansible.cfg file 
/etc/ansible/ansible.cfg
```
gathering = implicit
```
We can override ansible.cfg
1. ANSIBLE_GATHERING=explicit ansible-playbook playbook.yaml
2. export ANSIBLE_GATHERING=explicit && ansibel-playbook playbook.yaml
3. Create local copy of ansible.cfg
/opt/ansible.cfg
```
gathering = implicit
```

To view all conf
ansible-config list

To view currently config file
ansible-config view

To view curent setting
ansible-config dump