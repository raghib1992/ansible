# ansible.builtin
## ansible builtin collection rfer to modules and plugins shipped with ansible-core.

# ansible.legacy
## ansible legacy  collection is superset of ansible.builtin with 'custom' plugins int he configured path and adjacent directories

1. create folder
- name: plugins/action
2. create cusotm plugind
- debug.py
    - get this plugins from
    - ref for all plugins github repo *https://github.com/ansible/ansible*
    - ref debug plugins *https://github.com/ansible/ansible/blob/devel/lib/ansible/plugins/action/debug.py*
        - update msg line for test custom plugins
        - *result['msg'] = (new_module_args['msg']+"foo")*
3. Create
- ansible.cfg
```
[defaults]
action_plugins = plugins/action
```
4. Create invenroty file
```
# test on localhost
localhost ansible_connection=local
```
5. Create two playbook
```yaml
- name: debug module demo
  hosts: all
  vars:
    fruits: "apple"
  tasks:
    - name: Builtin
      ansible.builtin.debug:
        msg: "{{ fruits }}"
```

```yaml
- name: debug module demo
  hosts: all
  vars:
    fruits: "apple"
  tasks:
    - name: Legacy
    #   ansible.legacy.debug:
      debug:
        msg: "{{ fruits }}"
```