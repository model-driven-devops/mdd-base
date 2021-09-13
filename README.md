# Model-Driven Devops VA Repo

This is the base repo for Model-Driven devops.  It has the needed python requirements (requirements.txt) and
Ansible Collection (requirements.yml) to run a Model-Driven Devops pipeline.  It requires an inventory and
certain envrionment variables to be set.

# Installation
## Clone Repo
```
git clone git@github.com:model-driven-devops/mdd-base.git
```

## Depedancies
### Python 
```
python3 -m venv venv-mdd
. ./venv-mdd/bin/activate
pip3 install -r requirements.txt
```
### Ansible Collections
```
ansible-galaxy collection install -r collections/requirements.yml
```
> Note: If you want to develop a collection, you need to comment out the collection in requirements.yml and clone the collection repo directly, e.g.
```
cd ansible_colletions
mkdir ciscops
cd ciscops
git@github.com:model-driven-devops/ansible-mdd.git mdd
```

### Environment Variables
#### Netbox
```
export NETBOX_HOST=x.x.x.x
export NETBOX_API=https://x.x.x.x
export NETBOX_TOKEN=xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
```

#### NSO
```
export NSO_HOST=y.y.y.y
export NSO_HOST_URL=http://y.y.y.y:8080/jsonrpc
export NSO_USERNAME=admin
export NSO_PASSWORD=admin
```

#### CML
```
export CML_HOST=cml.domain.com
export CML_USERNAME=user
export CML_PASSWORD=password
export CML_LAB=mdd
export CML_VERIFY_CERT=false
```

# Playbooks
## Update OC
```
ansible-playbook ciscops.mdd.oc_update
```