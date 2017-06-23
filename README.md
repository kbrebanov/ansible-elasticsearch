elasticsearch
=============

[![Build Status](https://travis-ci.org/kbrebanov/ansible-elasticsearch.svg?branch=master)](https://travis-ci.org/kbrebanov/ansible-elasticsearch)

Installs and configures Elasticsearch

Requirements
------------

This role requires Ansible 1.9 or higher.

Role Variables
--------------

| Name                                             | Default              | Description                                                                                                    |
|:-------------------------------------------------|:---------------------|:---------------------------------------------------------------------------------------------------------------|
| elasticsearch_version                            | 5.4.2                | Version of Elasticsearch to install                                                                            |
| elasticsearch_action_destructive_requires_name   | true                 | Require explicit names when deleting indices                                                                   |
| elasticsearch_bootstrap_memory_lock              | false                | Lock the memory on startup                                                                                     |
| elasticsearch_heap_size                          | 1g                   | Heap size                                                                                                      |
| elasticsearch_http_port                          | 9200                 | Set a custom port for HTTP                                                                                     |
| elasticsearch_java_home                          | ''                   | Elasticsearch Java path                                                                                        |
| elasticsearch_java_opts                          | ''                   | Additional Java OPTS                                                                                           |
| elasticsearch_max_locked_memory                  | unlimited            | Maximum locked memory size                                                                                     |
| elasticsearch_max_map_count                      | 262144               | Maximum number of VMA (Virtual Memory Areas) a process can own                                                 |
| elasticsearch_max_open_files                     | 65535                | Maximum number of open files                                                                                   |
| elasticsearch_restart_on_upgrade                 | true                 | Configure restart on package upgrade                                                                           |
| elasticsearch_startup_sleep_time                 | 5                    | The number of seconds to wait before checking if Elasticsearch started successfully as a daemon process        |
| elasticsearch_cluster_name                       | ''                   | Use a descriptive name for your cluster                                                                        |
| elasticsearch_discovery_zen_minimum_master_nodes | 1                    | Prevent the "split brain" by configuring the majority of nodes (total number of master-eligible nodes / 2 + 1) |
| elasticsearch_discovery_zen_ping_unicast_hosts   | [127.0.0.1, '[::1]'] | Pass an initial list of hosts to perform discovery when new node is started                                    |
| elasticsearch_gateway_recover_after_nodes        | ''                   | Block initial recovery after a full cluster restart until N nodes are started                                  |
| elasticsearch_network_host                       | ''                   | Set the bind address to a specific IP (IPv4 or IPv6)                                                           |
| elasticsearch_node_name                          | ''                   | Use a descriptive name for the node                                                                            |
| elasticsearch_node_attr_rack                     | ''                   | Use a descriptive name for the node rack                                                                       |
| elasticsearch_path_data                          | []                   | Paths to directories where to store the data                                                                   |
| elasticsearch_path_logs                          | []                   | Paths to log files                                                                                             |

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
