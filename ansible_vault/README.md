# Create Encrypted file
ansible-vault create vars/users.yaml

# Encrypt existing clear text file
ansible-vault encrypt vars/users.yaml

# Decncrypt existing encrypted file
ansible-vault decrypt vars/users.yaml

# Edit encrypt file
ansible-vault edit vars/users.yaml

# VIew encrypted file
ansible-vault view vars/users.yaml