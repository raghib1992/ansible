# Default error handlin
if any task not operate, ansible not stop running task on other server

# to stop play alltogether is error occur in any server

- 
    name: install db
    server: server*
    any_error_fatal: true
    tasks:
        .......cont...