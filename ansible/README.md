# Ansible Playbooks

Those are the playbooks to setup two hosts for a Workadventure setup.
Two hosts must be availabe beforehand and the ips needs to be inserted into `inventory.yaml` in the coresponding group.
For that copy the template and insert your ips.

## Requirements

To install the requirements execute

```shell
ansible-galaxy install -r requirements.yaml
```

## workadventure.playbook.yaml

This will privision the hosts of the `workadventure` and `turn` group of `inventory.yaml`.

```shell
ansible-playbook -i inventory.yaml workadventure.playbook.yaml
```

