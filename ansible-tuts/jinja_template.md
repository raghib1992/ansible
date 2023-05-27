Filters highlighted by Ansible : 

https://docs.ansible.com/ansible/latest/user_guide/playbooks_filters.html

List of Jinja2 Filters :

https://jinja.palletsprojects.com/en/2.11.x/templates/#builtin-filters



Common used Filters : 

- {‌{ my_var | default("myval") }} : assign default value "myval" to the variable "my_var" if it not defined.

- {‌{ user_password | password_hash('sha512') }} : transform the variable value to a sha512 password hash . Useful when using "user" module to create/update users with their passwords.

- The following filters change the format of the variable data structure to json or yaml or even to a pretty json or yaml :

{‌{ some_variable | to_json }}
{‌{ some_variable | to_yaml }}
{‌{ some_variable | to_nice_json }}
{‌{ some_variable | to_nice_yaml }}

##############

Summary- Jinja2 Templating Syntax
This is a summary of the main Jinja2 Blocks syntax that can be used with Ansible playbook for daily basis operations and maintenance:



Print variable or Expression
Print the variable by using the variable name surrounded by double braces.

{‌{ my_var }}
# .i.e: {‌{ ansible_distribution }}


Filters
Variables can be transformed/modified by filters.

Think about filter as a function

{‌{ my_var | my_filter }}
# .i.e : {‌{ app_title | capitalize }}
Read it like my_filter(my_var)



If Block
{% if CONDITION1 %}
    blah blah blah
{% elif CONDITION2 %}
    blahelif blahelif blahelif .
{% else %}
    blahelse so far
{% endif %}
 
#.i.e
 
{% if git_branch == 'master' %}
     RELEASE: {‌{ app_version }}
{% else %}
    SNAPSHOT: {‌{ app_version }}-RC{‌{ build_number }} 
{% endif %}


For Loop
{% for ELEMENT in ARRAY %}
   Process {‌{ ELEMENT }}
{% endfor %}
 
#. i.e: assume that ( app_pages = ["login.html", "index.html"] )
 
{% for page in app_pages %}
   <a href="https://example.com/{‌{ page }}">{‌{ page }}</a>
{% endfor %}
