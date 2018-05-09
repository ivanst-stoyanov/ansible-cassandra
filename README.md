Cassandra
========

Ansible role to install and configure Cassandra (DataStax Distribution).

This role works for Cassandra 3.1 and greather. You can check the available versions here http://dl.bintray.com/apache/cassandra/dists/

*Note:* Recommended Java version is 8

*Note2:* The role is an updated version of https://github.com/wunzeco/ansible-cassandra

## Examples

```
- hosts: dbhost

  vars:
    cassandra_version: 3.11x
    cassandra_cluster_name: myAwesomeCluster
    cassandra_seeds: [ "seedIp1", "seedIp2" ]  			# List of IP Addresses ONLY
    cassandra_listen_address: "{{ ansible_eth0.ipv4.address }}"  
    cassandra_rpc_address: "{{ ansible_eth0.ipv4.address }}"

  roles:
    - ivanst-stoyanov.cassandra
```
> **INFO:** 
>
> 		If your seed nodes have DNS resolveable FQDNs, you may use 
>		**cassandra_seeds_fqdn** (instead of cassandra_seeds).

## Testing

To run integration tests of this role

```
kitchen verify && kitchen destroy
```

> **Note:**
>   `kitchen test` command is not appropriate for this role because both kitchen
>    suites (instances) need to be up and running for all tests to pass.


## Dependencies:

None
