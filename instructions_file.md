# Ansible Setup - Home MacOSX Environment


## Step 1 - Install Ansible and BOTO3 
- follow cook cutter example on ansible website 
- if will be creating, destorying, and stopping ec2 instaces, also be sure to install `boto` AND `boto3` - reference: https://docs.ansible.com/ansible/latest/modules/ec2_module.html
- go into ~/.aws/credentials and make sure the key and secret are up to date

## Step 2 - Create etc/ansible folder 
`mkdir /etc/ansible`

## Step 3 - Create config and host files 
### Configuration
`touch ansible.cfg`
- within this config file: 
```
[defaults]
private_key_file=path_to_my_key/my_key.pem
remote_user = ubuntu
```
### Hosts file 
`touch hosts`
- within this hosts file (onte - myServers is a tag and can be anything
- note - adding in the python_interpreter is key if you are running pyenv or a virtual environment
```
[datascience]
52.11.127.33

[localhost]
local ansible_connection=local ansible_python_interpreter=python
```

## Step 4 - Test with ping to ensure it works 
`ansible all -m ping`


