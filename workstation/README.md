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
ansible-playbook --ask-become-pass --extra-vars @extra_vars/USERNAME.yml workstation-setup-USERNAME.yml
```

When playbook providies files encrypted by `ansible-vault` (i.e. openvpn config
file), passing vault pass is additionally required:

```bash
--vault-password-file vault_pass.txt
```

Currently the default and tested usage is self-setup of the workstation on
localhost.

## Playbooks

Currently available playbooks are:

* `workstation-setup-base.yml`
  - roles suitable for every developer

* `workstation-setup-embedded.yml`
  - includes `worstation-setup-base.yml` playbook
  - adds roles suitable for embedded developer on top of it

* `workstation-setup-macpijan.yml`
  - includes `workstation-setup-base.yml` role
  - includes `workstation-setup-embedded.yml` role
  - add `macpijan` custom roles

## Packages

Currently packages are distributed into 3 groups:

* `packages_base` - suitable for every developer

* `pacages_embedded` - especially useful for embedded developers

* `packages_extra_*` - user-specific packages

## Modification

Additional playbooks with different host / packages configuration may be added

### Adding playbook for new user

* Create [playbook file](workstation-setup-embedded-dev-example.yml)

* Create [extra vars file](extra_vars/embedded-dev-example.yml)

* Add your template files to the roles used in playbook (if required). In this
  example adding templates for roles:
  - `ohmyzsh`
  - `vim`
  - `tmux`
  is necessary.
