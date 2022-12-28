# Ansible Playbooks

Those are the playbooks to setup two hosts for a Workadventure setup.
Two hosts must be availabe beforehand and the ips needs to be inserted into `inventory.yaml` in the coresponding group.
For that copy the template and insert your ips.

Example:

```yaml
all:
  children:
    workadventure:
      hosts:
        127.0.159.1 # Workadventure will run here
    turn:
      hosts:
        127.0.159.2 # The TURN server will run here
```

## Requirements

To install the requirements execute

```shell
ansible-galaxy install -r requirements.yaml
pip3 install hcloud
```

## workadventure.playbook.yaml

This will privision the hosts of the `workadventure` and `turn` group of `inventory.yaml`.

```shell
ansible-playbook -i inventory.yaml workadventure.playbook.yaml
```

## Automatic Hetzner Deploy

With the help of the `hetzner_token` variable in the `inventory.yaml` and the `hetzner.playbook.yaml` two server can be automatically provisioned.
For how to get an api-token look [here](https://docs.hetzner.com/de/cloud/api/getting-started/generating-api-token).

At the end the two ips of the servers will be outputted, to allow you to the your DNS and `.env` file to this ips.

To setup hosts:

```shell
ansible-playbook -i inventory.yaml --extra-vars "state=present public_key=~/.ssh/<yourpublickey>" hetzner.playbook.yaml
```

To destroy the hosts

```shell
ansible-playbook -i inventory.yaml --extra-vars "state=absent" hetzner.playbook.yaml
```

## Jitsi with Ansible

There is also a ansible playbook for hosting jitsi: https://github.com/udima-university/ansible-jitsi-meet
