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
Now run:
```shell
ansible-playbook -i inventory.yaml playbook.yaml
```
## Usage
Navigate to `http://<remote-host>:3000` and create an admin login. Now navigate to `http://<remote-host>:3000/admin/settings/` and click on `models` and `manage models` (looks like a small download link). In the `Pull a model from Ollama.com` box enter `deepseek-r1:1.5b` or whatever model you want to run.
