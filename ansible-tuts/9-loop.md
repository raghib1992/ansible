## loop of array
```yml
- name:
  hosts:
  become:
  vars:
  tasks:
    - user: name='{{ item }}' state=present
      loop:
       - joe
       - george
       - ravi
       - kiran
       - jazlan
       - emaan
       - mazin
       - izaan
```
## loop of array of dict

```yml
- name:
  hosts:
  become:
  vars:
  tasks:
    - user: name='{{ item.name }}' state=present uid=''{{ item.uid }}
      loop:
       - name: joe
         uid: 1001
       - name: george
         uid: 1002
       - name: ravi
         uid: 1003
       - name: kiran
         uid: 1004
       - name: jazlan
         uid: 1005
       - name: emaan
         uid: 1006
       - name: mazin
         uid: 1007
       - name: izaan
         uid: 1008
```

## with_*
### with_file
### with_url
### with_mongodb
### with_items
```yml
- name:
  hosts:
  become:
  vars:
  tasks:
    - user: name='{{ item }}' state=present
      with_items:
       - joe
       - george
       - ravi
       - kiran
       - jazlan
       - emaan
       - mazin
       - izaan
```
```yml
---
-  name: 'Print list of fruits'
   hosts: localhost
   vars:
     fruits:
       - Apple
       - Banana
       - Grapes
       - Orange
   tasks:
     - command: 'echo "{{ item }}"'
       with_items:
         - '{{ fruits }}'
```