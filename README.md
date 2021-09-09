# mdd-base
Model-Driven Devops Base Repo

# Installation
## Clone Repo
```
git clone git@github.com:model-driven-devops/mdd-base.git
```

## Add Depednancies
```
python3 -m venv venv-mdd
. ./venv-mdd/bin/activate
pip3 install -r requirements.txt
ansible-galaxy collection install -r requirements.yml
```

## Add Inventory
```
cd inventory
git clone git@github.com:model-driven-devops/mdd-inventory.git
```

# Playbooks
## Update OC System
```
ansible-playbook -i inventory/mdd-inventory ciscops.mdd.update_system
```

## Update OC Interfaces
```
ansible-playbook -i inventory/mdd-inventory ciscops.mdd.update_interfaces
```