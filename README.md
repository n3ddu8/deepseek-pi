# Deepseek Pi
Using Ansible and Docker Compose, run Ollama with Open WebUI to host and interact with models such as Deepseek R1. This is just a bit of fun, and isn't really usable in real-world scenarios. For comparison, the Deepseek R1 that at the time of writing is supposedly beating ChatGPT runs with 671 billion parameters, whereas the the only version that works on a standard Pi uses 1.5 billion parameters.


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
