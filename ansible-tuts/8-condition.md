```yml
- 
  name: out in register
  hosts: localhost
  tasks:
    - name: Shut down Debian flavored systems
      ansible.builtin.command: /sbin/shutdown -t now
        when: ansible_facts['os_family'] == "Debian"
        when: ansible_os_family == "Redhat" or
              ansible_os_family == "SUSE"
```

```yml
- 
 name: loop
 hosts: all
 vars:
    packages:
        - name: nginx
          required: True
        - name: mysql
          required: True
        - name: apache
          required: False
 tasks:
   - name: Install packages {{ item.name }} in loop 
     ansible.builtin.yum:
       name: "{{ item.name }}"
       state: present
     when: item.required == True
     loop: "{{ packages }}"
```

### Condition with register
```yml
- 
  name: out in register
  hosts: localhost
  tasks:
    - name: Shut down Debian flavored systems
      ansible.builtin.command: service hhtpd status
      register: result
    - mail:
        to: a@a.com
        subject: test
        body: This is for testing
        when: result.stdout.find('down') != -1