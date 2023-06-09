# Must have python>=3.6 install
Install pyhton3
python3 --version
sudo apt install -y python3

# Must have boto3>=1.16.0
pip3 show boto3
pip3 install boto3

### If pip3 is not available
sudo apt install python3-pip

# Must have botocore>= 1.19.0
pip3 show botocore | grep Version

# Install amazon.aws role
ansible-galaxy collection install amazon.aws

# edit ansible.cfg in [inventory]
enable_plugins = aws_ec2

# create aws_ec2.yaml
### Ref https://docs.ansible.com/ansible/latest/collections/amazon/aws/aws_ec2_inventory.html#ansible-collections-amazon-aws-aws-ec2-inventory
```
plugin: aws_ec2
regions:
  - ap-south-1
profile: default
filters:
  tag:env: dev
```

## List all available host in mention region
ansible-inventory -i ./aws_ec2.yaml list


ansible aws_ec2 -i ./aws_ec2.yaml -m ping --private-key=./mumbai-key.pem -u ec2-user

Ref https://docs.ansible.com/ansible/2.8/user_guide/intro_dynamic_inventory.html#inventory-script-example-aws-ec