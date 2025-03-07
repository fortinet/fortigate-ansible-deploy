# Deployment of a FortiGate-VM(BYOL/PAYG)  on the Azure
## Introduction
An ansible script to deploy a FortiGate-VM(BYOL/PAYG) on Azure

## Requirements
* [Ansible](https://docs.ansible.com/ansible/latest/getting_started/index.html) >= 2.17.9
* jinja >= 3.1.5
* azure.azcollection >= 2.7.0


## Deployment overview
Ansbile deploys the following components:
   - Azure Virtual Network with 2 subnets
   - One FortiGate-VM instances with 2 NICs

## Deployment
To deploy the FortiGate-VM to Azure:
1. Clone the repository.
2. Customize variables in the `env.conf.example` and `fortigate_vars.yml` file as needed. And rename `env.conf.example` to `env.conf`
3. Export env.conf for ansible credentials
   ```sh
   $ source env.conf
    ```
4. Run the playbook:
   ```sh
   $ ansible-playbook main.yml
    ```
   ```
5. Once finish running, it will have the following.

Output will include the information necessary to log in to the FortiGate-VM instances:
```sh
"msg": "The public IP address: <FGT Public IP>  Resource group : <Resource Group name> Username: <FGT Username> Password: <FGT Password> "
```

## Destroy the instance
To destroy the instance, use the command:
```sh
$ ansible-playbook delete_rg.txt 
```

# Support
Fortinet-provided scripts in this and other GitHub projects do not fall under the regular Fortinet technical support scope and are not supported by FortiCare Support Services.
For direct issues, please refer to the [Issues](https://github.com/fortinet/fortigate-ansible-deploy/issues) tab of this GitHub project.
For other questions related to this project, contact [github@fortinet.com](mailto:github@fortinet.com).

## License
[License](https://github.com/fortinet/fortigate-ansible-deploy/blob/master/LICENSE) © Fortinet Technologies. All rights reserved.

