# c01110011.hisohiso
Ansible roles for deploying and managing a self-hosted hisohiso encrypted chat server

## Requirements 
Ansible >= 2.15, Ubuntu 22.04/24.04, Docker (pre-installed on the host — the collection does not install Docker)

## Installation
```shell
  ansible-galaxy collection install c01110011.hisohiso
```

## Roles
| role         | description host                                                                                                                               |
|--------------|------------------------------------------------------------------------------------------------------------------------------------------------|
| server       | clones the repository, writes the .env configuration, and runs docker compose to deploy or update the application                              |
| host         | bootstraps the host OS: installs required packages, configures UFW firewall, fail2ban, unattended-upgrades, and creates a non-root deploy user |
| ssh_lockdown | hardens SSH by disabling root login and restricting access to the deploy user; run this only after verifying the deploy user works             |

## Development

### Requirements
- uv
- ansible-core

```shell
uv venv
source .venv/bin/activate
uv pip install -r requirements.txt
ansible-galaxy collection install -r requirements.yml
```

```shell
mkdir -p ~/.ansible/collections/ansible_collections/c01110011
ln -s $(pwd) ~/.ansible/collections/ansible_collections/c01110011/hisohiso
```

## License 
MIT

