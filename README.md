elasticsearch
=============

[![Build Status](https://travis-ci.org/kbrebanov/ansible-elasticsearch.svg?branch=master)](https://travis-ci.org/kbrebanov/ansible-elasticsearch)

Installs and configures Elasticsearch

Requirements
------------

This role requires Ansible 1.9 or higher.

Role Variables
--------------

| Name                                                                       | Default                                          | Description                                                                                             |
|:---------------------------------------------------------------------------|:-------------------------------------------------|:--------------------------------------------------------------------------------------------------------|
| elasticsearch_version                                                      | 2.4.1                                            | Version of Elasticsearch to install                                                                     |
| elasticsearch_action_destructive_requires_name                             | true                                             |                                                                                                         |
| elasticsearch_bootstrap_mlockall                                           | false                                            | Set this property to true to lock the memory                                                            |
| elasticsearch_direct_size                                                  | ''                                               | Max direct memory                                                                                       |
| elasticsearch_heap_size                                                    | 1g                                               | Heap size                                                                                               |
| elasticsearch_heap_newsize                                                 | ''                                               | Heap new generation                                                                                     |
| elasticsearch_java_opts                                                    | ''                                               | Additional Java OPTS                                                                                    |
| elasticsearch_max_locked_memory                                            | unlimited                                        | Maximum locked memory size                                                                              |
| elasticsearch_max_map_count                                                | 262144                                           | Maximum number of VMA (Virtual Memory Areas) a process can own                                          |
| elasticsearch_max_open_files                                               | 65535                                            | Maximum number of open files                                                                            |
| elasticsearch_restart_on_upgrade                                           | true                                             | Configure restart on package upgrade                                                                    |
| elasticsearch_startup_sleep_time                                           | 5                                                |                                                                                                         |
| elasticsearch_cluster_blocks_read_only                                     | false                                            |                                                                                                         |
| elasticsearch_cluster_info_update_interval                                 | 30s                                              |                                                                                                         |
| elasticsearch_cluster_name                                                 | elasticsearch                                    | Cluster name identifies your cluster for auto-discovery                                                 |
| elasticsearch_cluster_routing_allocation_allow_rebalance                   | indices_all_active                               |                                                                                                         |
| elasticsearch_cluster_routing_allocation_awareness_attributes              | []                                               |                                                                                                         |
| elasticsearch_cluster_routing_allocation_awareness_force_zone_values       | []                                               |                                                                                                         |
| elasticsearch_cluster_routing_allocation_balance_index                     | 0.55f                                            |                                                                                                         |
| elasticsearch_cluster_routing_allocation_balance_shard                     | 0.45f                                            |                                                                                                         |
| elasticsearch_cluster_routing_allocation_balance_threshold                 | 1.0f                                             |                                                                                                         |
| elasticsearch_cluster_routing_allocation_cluster_concurrent_rebalance      | 2                                                |                                                                                                         |
| elasticsearch_cluster_routing_allocation_disk_include_relocations          | true                                             |                                                                                                         |
| elasticsearch_cluster_routing_allocation_disk_threshold_enabled            | true                                             |                                                                                                         |
| elasticsearch_cluster_routing_allocation_disk_watermark_high               | 90%                                              |                                                                                                         |
| elasticsearch_cluster_routing_allocation_disk_watermark_low                | 85%                                              |                                                                                                         |
| elasticsearch_cluster_routing_allocation_enable                            | all                                              |                                                                                                         |
| elasticsearch_cluster_routing_allocation_exclude                           | []                                               |                                                                                                         |
| elasticsearch_cluster_routing_allocation_include                           | []                                               |                                                                                                         |
| elasticsearch_cluster_routing_allocation_node_concurrent_recoveries        | 2                                                |                                                                                                         |
| elasticsearch_cluster_routing_allocation_node_initial_primaries_recoveries | 4                                                |                                                                                                         |
| elasticsearch_cluster_routing_allocation_require                           | []                                               |                                                                                                         |
| elasticsearch_cluster_routing_allocation_same_shard_host                   | false                                            |                                                                                                         |
| elasticsearch_cluster_routing_rebalance_enable                             | all                                              |                                                                                                         |
| elasticsearch_discovery_zen_fd_ping_interval                               | 1s                                               |                                                                                                         |
| elasticsearch_discovery_zen_fd_ping_retries                                | 3                                                |                                                                                                         |
| elasticsearch_discovery_zen_fd_ping_timeout                                | 30s                                              |                                                                                                         |
| elasticsearch_discovery_zen_join_timeout                                   | 60s                                              |                                                                                                         |
| elasticsearch_discovery_zen_master_election_filter_client                  | true                                             |                                                                                                         |
| elasticsearch_discovery_zen_master_election_filter_data                    | false                                            |                                                                                                         |
| elasticsearch_discovery_zen_minimum_master_nodes                           | 1                                                | Set to ensure a node sees N other master eligible nodes to be considered operational within the cluster |
| elasticsearch_discovery_zen_no_master_block                                | write                                            |                                                                                                         |
| elasticsearch_discovery_zen_ping_unicast_hosts                             | [127.0.0.1, '[::1]']                             | List of master nodes in the cluster                                                                     |
| elasticsearch_discovery_zen_ping_timeout                                   | 3s                                               |                                                                                                         |
| elasticsearch_discovery_zen_publish_timeout                                | 30s                                              |                                                                                                         |
| elasticsearch_gateway_expected_data_nodes                                  | 0                                                |                                                                                                         |
| elasticsearch_gateway_expected_master_nodes                                | 0                                                |                                                                                                         |
| elasticsearch_gateway_expected_nodes                                       | 0                                                | Set how many nodes are expected in this cluster                                                         |
| elasticsearch_gateway_recover_after_data_nodes                             | ''                                               |                                                                                                         |
| elasticsearch_gateway_recover_after_master_nodes                           | ''                                               |                                                                                                         |
| elasticsearch_gateway_recover_after_nodes                                  | ''                                               | Allow recovery process after N nodes in a cluster are up                                                |
| elasticsearch_gateway_recover_after_time                                   | 5m                                               | Set the timeout to initiate the recovery process, once elasticsearch_gateway_recover_after_nodes are up |
| elasticsearch_http_bind_host                                               | "{{ elasticsearch_http_host }}"                  |                                                                                                         |
| elasticsearch_http_compression                                             | false                                            |                                                                                                         |
| elasticsearch_http_compression_level                                       | 6                                                |                                                                                                         |
| elasticsearch_http_cors_allow_credentials                                  | false                                            |                                                                                                         |
| elasticsearch_http_cors_allow_headers                                      | [X-Requested-With, Content-Type, Content-Length] |                                                                                                         |
| elasticsearch_http_cors_allow_methods                                      | [OPTIONS, HEAD, GET, POST, PUT, DELETE]          |                                                                                                         |
| elasticsearch_http_cors_allow_origin                                       | ''                                               |                                                                                                         |
| elasticsearch_http_cors_enabled                                            | false                                            |                                                                                                         |
| elasticsearch_http_cors_max_age                                            | 1728000                                          |                                                                                                         |
| elasticsearch_http_detailed_errors_enabled                                 | true                                             |                                                                                                         |
| elasticsearch_http_enabled                                                 | true                                             |                                                                                                         |
| elasticsearch_http_host                                                    | "{{ elasticsearch_network_host }}"               |                                                                                                         |
| elasticsearch_http_max_content_length                                      | 100mb                                            |                                                                                                         |
| elasticsearch_http_max_header_size                                         | 8kb                                              |                                                                                                         |
| elasticsearch_http_max_initial_line_length                                 | 4kb                                              |                                                                                                         |
| elasticsearch_http_pipelining                                              | true                                             |                                                                                                         |
| elasticsearch_http_pipelining_max_events                                   | 10000                                            |                                                                                                         |
| elasticsearch_http_port                                                    | 9200-9300                                        |                                                                                                         |
| elasticsearch_http_publish_host                                            | "{{ elasticsearch_http_host }}"                  |                                                                                                         |
| elasticsearch_http_publish_port                                            | ''                                               |                                                                                                         |
| elasticsearch_indices_breaker_fielddata_limit                              | ''                                               |                                                                                                         |
| elasticsearch_indices_breaker_fielddata_overhead                           | 1.03                                             |                                                                                                         |
| elasticsearch_indices_breaker_request_limit                                | ''                                               |                                                                                                         |
| elasticsearch_indices_breaker_request_overhead                             | 1                                                |                                                                                                         |
| elasticsearch_indices_breaker_total_limit                                  | ''                                               |                                                                                                         |
| elasticsearch_indices_fielddata_cache_size                                 | ''                                               |                                                                                                         |
| elasticsearch_indices_queries_cache_size                                   | 10%                                              |                                                                                                         |
| elasticsearch_indices_memory_index_buffer_size                             | 10%                                              |                                                                                                         |
| elasticsearch_indices_memory_max_index_buffer_size                         | ''                                               |                                                                                                         |
| elasticsearch_indices_memory_min_index_buffer_size                         | 48mb                                             |                                                                                                         |
| elasticsearch_indices_memory_min_shard_index_buffer_size                   | 4mb                                              |                                                                                                         |
| elasticsearch_indices_requests_cache_size                                  | ''                                               |                                                                                                         |
| elasticsearch_indices_requests_cache_expire                                | ''                                               |                                                                                                         |
| elasticsearch_indices_recovery_compress                                    | true                                             |                                                                                                         |
| elasticsearch_indices_recovery_concurrent_small_file_streams               | 2                                                |                                                                                                         |
| elasticsearch_indices_recovery_concurrent_streams                          | 3                                                |                                                                                                         |
| elasticsearch_indices_recovery_file_chunk_size                             | 512kb                                            |                                                                                                         |
| elasticsearch_indices_recovery_max_bytes_per_sec                           | 40mb                                             |                                                                                                         |
| elasticsearch_indices_recovery_translog_ops                                | 1000                                             |                                                                                                         |
| elasticsearch_indices_recovery_translog_size                               | 512kb                                            |                                                                                                         |
| elasticsearch_indices_ttl_bulk_size                                        | 10000                                            |                                                                                                         |
| elasticsearch_indices_ttl_interval                                         | 60s                                              |                                                                                                         |
| elasticsearch_network_bind_host                                            | "{{ elasticsearch_network_host }}"               |                                                                                                         |
| elasticsearch_network_host                                                 | [_local_]                                        |                                                                                                         |
| elasticsearch_network_publish_host                                         | []                                               |                                                                                                         |
| elasticsearch_network_tcp_keep_alive                                       | true                                             |                                                                                                         |
| elasticsearch_network_tcp_no_delay                                         | true                                             |                                                                                                         |
| elasticsearch_network_tcp_receive_buffer_size                              | ''                                               |                                                                                                         |
| elasticsearch_network_tcp_reuse_address                                    | true                                             |                                                                                                         |
| elasticsearch_network_tcp_send_buffer_size                                 | ''                                               |                                                                                                         |
| elasticsearch_node_data                                                    | true                                             | Allow this node to store data                                                                           |
| elasticsearch_node_master                                                  | true                                             | Allow this node to be eligible as a master node                                                         |
| elasticsearch_node_max_local_storage_nodes                                 | 1                                                |                                                                                                         |
| elasticsearch_node_name                                                    | ''                                               | Node name                                                                                               |
| elasticsearch_node_rack                                                    | ''                                               |                                                                                                         |
| elasticsearch_path_data                                                    | []                                               |                                                                                                         |
| elasticsearch_path_logs                                                    | []                                               |                                                                                                         |

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
