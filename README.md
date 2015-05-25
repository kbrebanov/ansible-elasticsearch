elasticsearch
=============

Installs and configures Elasticsearch

Requirements
------------

This role requires Ansible 1.4 or higher.

Role Variables
--------------

| Name                                   | Default       | Description                                                |
|----------------------------------------|---------------|------------------------------------------------------------|
| elasticsearch_version                  | 1.5           | Version of Elasticsearch to install                        |
| elasticsearch_cluster_name             | elasticsearch | Cluster name identifies your cluster for auto-discovery    |
| elasticsearch_node_master              | 'true'        | Allow this node to be eligible as a master node            |
| elasticsearch_node_data                | 'true'        | Allow this node to store data                              |
| elasticsearch_index_number_of_shards   | 5             | Set the number of shards (splits) of an index              |
| elasticsearch_index_number_of_replicas | 1             | Set the number of replicas (additional copies) of an index |

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
