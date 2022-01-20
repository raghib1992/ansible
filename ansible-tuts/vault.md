# Vault
## TO create a file in encrypted format
```
ansible-vault create <file-name.yml>
```
#### It will prompting for password
## To view the dat
```
ansible-vault view <file-name>
```
## To edit the vault file
```
ansible-vault edit <file-name>
```
## to decrypt
```
ansible-vault decrypt <file-name>
```
## to encrytpt the vault
```
ansible-vault encrypt <file-name>
```
#### promplted for password
*****************************
# To use vault with playbook
```
ansible-playbook my-playbook.yaml -i hosts-file --ask-vault-pass
```
```
ansible-playbook my-playbook.yaml -i hosts-file --vault-password-file pass.yaml
```
### pass.yaml file has the password of the vault file
