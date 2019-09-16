# Role for DNS zone management in AZURE
----------------------------------

**This DNS Ansible role**, can allow you to create one or a multiple DNS zone into your Azure account.

## Overview
----------------------------------
A simple role to manage your Zone you can use for your next Azure infrastructure project


## Requirements
----------------------------------
- Ansible 2.8.4
- AZ cli 2.0.52
- Azure 2.0.0
- python 2.7


## Installation
---------------------------------

First, make sur you have [Ansible](https://www.ansible.com/)  and [azcli](https://docs.microsoft.com/en-us/cli/azure/install-azure-cli?view=azure-cli-latest) on your machine.


## Usage
---------------------------------


You can use this playbook by modify variables as you need. And tun the command below to provision your DNS zone:
```
ansible-playbook -i tests/inventory tests/main.yml
```

If you want to delete the ZONE just run:

```
ansible-playbook -i tests/inventory tests/main.yml -e"state=absent"
```
 Note that you can create more than one at once by duplicate the domain name block from defaults variables like this:

```
 domain_definitions:
   - domain_name: domain01.com
     resource_group: resource_group
     type: private
   - domain_name: domain02.com
     resource_group: resource_group
     type: private
```

In this examples you'll create two DNS zones.


## Variables
-----------------------------------------------

#### GENERAL

| Name | Description | Type | Default | Required |
|------|-------------|:----:|:-----:|:-----:|
| domain_name | Variable for your domain name | string | - | yes |
| resource_group | The resource group targeted for this DNS zone | string | - | yes |
| type | The type of the DNS zone private or public| string | - | yes |







## Contributing
---------------------------------
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.



## Next improvements
----------------------------------

## Author
----------------------------------
- [Sype](https://github.com/sype), DevOps engineer.

## Acknowlegement
----------------------------------
Thank Wefactorit Team.
