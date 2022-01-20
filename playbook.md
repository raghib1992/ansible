-
  name: connectivity test between host and target machine
  hosts: all
  tasks:
    - name: ping test
      ping:

-
  name: Deploy a mysql DB
  hosts: db_server
  roles:
    - python
    - mysql_db

-
  name: Deploy a Web Server
  hosts: web_server
  roles:
    - role: mysql
      become: yes
      vars:
        mysql_user_name: dbadmin