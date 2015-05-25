elasticsearch
=============

Installs and configures Elasticsearch

Requirements
------------

This role requires Ansible 1.4 or higher.

Role Variables
--------------

| Name                  | Default | Description                         |
|-----------------------|---------|-------------------------------------|
| elasticsearch_version | 1.5     | Version of Elasticsearch to install |

Dependencies
------------

- kbrebanov.java (OpenJDK 8)

Example Playbook
----------------

Install Elasticsearch
```
- hosts: all
  roles:
    - { role: kbrebanov.elasticsearch }
```

License
-------

BSD

Author Information
------------------

Kevin Brebanov
