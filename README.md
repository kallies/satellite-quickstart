# Ansible Satellite Quickstart

## Bootstrap

From a newly clone repository, invoke

```
% export ANSIBLE_GALAXY_SERVER_AUTOMATION_HUB_TOKEN=...
% ansible-galaxy role install -r requirements.yml --server https://galaxy.ansible.com
% ansible-galaxy collection install -r requirements.yml
```

to download all role dependencies.

For downloading collections from the Automation Hub you need to set the
environment variable `ANSIBLE_GALAXY_SERVER_AUTOMATION_HUB_TOKEN` which
can be obtained from <https://cloud.redhat.com/ansible/automation-hub/token>.

Manual way: `ansible-galaxy collection install redhat.satellite.tar.gz -p ./collections`

The [Satellite documentation](https://access.redhat.com/documentation/en-us/red_hat_satellite/6.14/html/administering_red_hat_satellite/managing_project_with_ansible_collections_admin) describes an alternative rpm based installation.

```
satellite-maintain packages install ansible-collection-redhat-satellite
```

## Collection Documentation

Offline:

```
ansible-doc redhat.satellite.content_view
```

Or if you're on a recent ansible version, use `ansible-navigator`.

[Online](https://redhatsatellite.github.io/satellite-ansible-collection/)


## Playbook Example

```
ansible-playbook --ask-vault-pass playbooks/satellite-main.yml
```
