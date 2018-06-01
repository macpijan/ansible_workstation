Workstation Ansible
===================

This repository aims to gather information about all workstation and servers
used in 3mdeb infrastructure. The goal of gathering those information is
further deployment and management automation through Ansible.

# Managing host prerequisites

```
virtualenv ansible-venv
source ansible-venv/bin/activate
pip install ansible
ansible-galaxy install angstwad.docker_ubuntu
ansible-galaxy install debops.apt_preferences
ssh-keygen -f ~/.ssh/ansible
ssh-add ~/.ssh/ansible
ssh-copy-id -i ~/.ssh/ansible <user>@<target_host>
```

# Tested on version

```
(ansible-venv) [18:01:03] pietrushnic:3mdeb $ ansible --version
ansible 2.5.2
  config file = None
  configured module search path = [u'/home/pietrushnic/.ansible/plugins/modules', u'/usr/share/ansible/plugins/modules']
  ansible python module location = /home/pietrushnic/storage/ansible-venv/local/lib/python2.7/site-packages/ansible
  executable location = /home/pietrushnic/storage/ansible-venv/bin/ansible
  python version = 2.7.15 (default, May  1 2018, 05:55:50) [GCC 7.3.0]
```

Faroth
------

PXE and NFS server which rely on [pxe-server container](https://hub.docker.com/r/3mdeb/pxe-server/). This is QEMU VM
with Debian template installed - more information [here](https://github.com/3mdeb/pxe-server).

# How to run playbook

```shell
cd faroth
ansible-playbook -b --ask-become-pass pxe-server-setup.yml
```

Contribution
------------

Before contributing your changes please check those with `ansible-lint` and
`ansible-review`.

