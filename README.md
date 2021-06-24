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

### redhat.satellite dependency

Satellite playbooks need to be executed on a api-host where
[`python2-apypie`](https://yum.theforeman.org/client/2.3/el7/x86_64/python2-apypie-0.2.2-1.el7.noarch.rpm)
is installed.

## Collection Documentation

```
ansible-doc redhat.satellite.content_view
```

## Playbook Example

```
ansible-playbook playbooks/locations.yml
```