# Linear strategy
Ansible run one task in all the server and wait to complete until it install the task in all the server

# Free Strategy
in this case, ansible will not wait for to complete the task in all the server, it run next task on the server in which the first task complete

In this scenario, we have to mention strategy, otherwise ansible run default strategy which is Linear

- name: install db
  strategy: free
  hosts: server1, server2, server3
  tasks:
    .......cont..


# strategy Batch
ansible play Linear strategy but on the no. of server mention in playbook
- name: install db
  serial: 3
  hosts: server1, server2, server3
  tasks:
    .......cont..

# fork
ansible/cfg
fork = 5  # at a time by default ansible run task on 5 server.

