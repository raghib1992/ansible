Verify ansible playbook
1. check mode
- dry run
- allow preview of playbook without applying them 
- use the --check option to run a playbook in check mode
```
ansible-playbook -i inventory playbook.yaml --check
```

2. diff mode
- provides a before and after comparison of playbook changes
- understand  and verify the impact of playbook changes before applying them 
- Utlize the --diff option to run a playbook in diff mode
```
ansible-playbook -i inventory playbook.yaml --check --diff
```

3. To check syntax error use --syntax-check
```
ansible-playbook -i inventory playbook.yaml --syntax-check
```

4. Ansible lint
- Ansible lint is command line tool  that perform linting on ansible playbook, roles, and collectionas.
```
ansible-lint playbok.yaml
```