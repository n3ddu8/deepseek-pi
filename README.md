# Deepseek Pi
Run Deepseek R1 on a Raspberry Pi

## Setup
### Inventory File
Configure `inventory.yaml` with the details of the target machine.
### SSH
Run the following, following the onscreen instructions where necerssary:
```shell
ssh-keygen
ssh-copy-id <remote-user>@<remote-host>
ansible -i inventory.yaml all -m ping
```
This should return a `pong`.
## Usage
Run:
```shell
ansible-playbook -i inventory.yaml playbook.yaml
```
