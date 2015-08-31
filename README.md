Boostrap Ubuntu
==========================

This repository contains a basic Ansible role used for bootstrapping an Ubuntu server.

The included tasks are:

- Copy configuration files
- Configure locale
- Install and update Ubuntu packages
- Basic security configuration:
    * Disable SSH root access
    * Disable password authentication
    * Install Fail2ban

Forked from https://github.com/mozodev/bootstrap-ubuntu and modified, which in turn was
forked from https://github.com/diec123/ansible-bootstrap and modified.


Requirements
------------
[Ansible](https://github.com/ansible/ansible) (1.4 above)


Role Variables
--------------

```
locale: en_US.UTF-8
language: 'en_US:en'
timezone: US/Pacific

ssh_port: 22

common_system_packages:
    - curl
    - wget
    - build-essential
    - python-software-properties
    - mcrypt
    - git
```

Note: if a list variable named required_system_packages exists in the parent playbook, the contents of that list will be merged into `common_system_packages` at the point when system packages are installed.

Dependencies
------------
none.


Example Playbook
----------------

    - hosts: servers
      roles:
         - { role: dltj.bootstrap-ubuntu }

License
-------

MIT License
