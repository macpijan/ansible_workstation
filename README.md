# Ansible workstation self-setup

## Prerequisites

* Installed system (tested with Ubuntu 18.04)

* Created user with `sudo` access

* Installed `ansible`

```bash
sudo apt install ansible
```

## Usage

```bash
ansible-pull --url git@github.com:macpijan/ansible_workstation.git --ask-become-pass PLAYBOOK
```

## Playbooks

Currently available playbooks are:

* `workstation-self-setup.yml`

## Packages

Currently packages are distributed into 3 groups:

* `packages_base` - suitable for every developer

* `pacages_embedded` - especially useful for embedded developers

* `packages_extra_*` - user-specific packages

## Modification

Additional playbooks with different host / packages configuration may be added
