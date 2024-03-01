### loop
```yml
---
- 
  name: Create user
  hosts: all
  tasks:
    - user: name='{{ item }}' state=present
      loop:
        - nadim
        - jitender
        - Israr
        - Waquar
        - Murad
        - Zaman
- 
  name: Create user
  hosts: all
  tasks:
    - user: name='{{ item }}' state=present
      loop:
        - nadim
        - jitender
        - Israr
        - Waquar
        - Murad
        - Zaman

```