elasticsearch
=============

[![Ansible Galaxy](https://img.shields.io/badge/galaxy-kbrebanov.elasticsearch-660198.svg)](https://galaxy.ansible.com/list#/roles/3923)

Installs and configures Elasticsearch

Requirements
------------

This role requires Ansible 1.4 or higher.

Role Variables
--------------

| Name                                           | Default       | Description                                                                                             |
|------------------------------------------------|---------------|---------------------------------------------------------------------------------------------------------|
| elasticsearch_version                          | 1.7.1         | Version of Elasticsearch to install                                                                     |
| elasticsearch_cluster_name                     | elasticsearch | Cluster name identifies your cluster for auto-discovery                                                 |
| elasticsearch_node_name                        | ''            | Node name                                                                                               |
| elasticsearch_node_master                      | 'true'        | Allow this node to be eligible as a master node                                                         |
| elasticsearch_node_data                        | 'true'        | Allow this node to store data                                                                           |
| elasticsearch_index_number_of_shards           | 5             | Set the number of shards (splits) of an index                                                           |
| elasticsearch_index_number_of_replicas         | 1             | Set the number of replicas (additional copies) of an index                                              |
| elasticsearch_heap_size                        | 256m          | Heap size                                                                                               |
| elasticsearch_heap_newsize                     | ''            | Heap new generation                                                                                     |
| elasticsearch_direct_size                      | ''            | Max direct memory                                                                                       |
| elasticsearch_max_open_files                   | 65535         | Maximum number of open files                                                                            |
| elasticsearch_max_locked_memory                | unlimited     | Maximum locked memory size                                                                              |
| elasticsearch_max_map_count                    | 262144        | Maximum number of VMA (Virtual Memory Areas) a process can own                                          |
| elasticsearch_java_opts                        | ''            | Additional Java OPTS                                                                                    |
| elasticsearch_restart_on_upgrade               | 'true'        | Configure restart on package upgrade                                                                    |
| elasticsearch_bootstrap_mlockall               | 'false'       | Set this property to true to lock the memory                                                            |
| elasticsearch_discovery_minimum_master_nodes   | ''            | Set to ensure a node sees N other master eligible nodes to be considered operational within the cluster |
| elasticsearch_discovery_ping_multicast_enabled | 'true'        | Set to 'false' to enable unicast discovery and disable multicast                                        |
| elasticsearch_discovery_ping_unicast_hosts     | '[]'          | List of master nodes in the cluster                                                                     |
| elasticsearch_gateway_recover_after_nodes      | ''            | Allow recovery process after N nodes in a cluster are up                                                |
| elasticsearch_gateway_expected_nodes           | ''            | Set how many nodes are expected in this cluster                                                         |
| elasticsearch_gateway_recover_after_time       | ''            | Set the timeout to initiate the recovery process, once elasticsearch_gateway_recover_after_nodes are up |

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

Install specific version of Elasticsearch
```
- hosts: all
  roles:
    - { role: kbrebanov.elasticsearch, elasticsearch_version: 1.1.1 }
```

License
-------

BSD

Author Information
------------------

Kevin Brebanov
