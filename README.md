# Ansible roles for Prometheus exporters

Set of Ansible roles for Prometheus exporters.

## System Requirements

These roles have only been tested with:

 * CentOS 7
 * Ansible version:
   * 2.9.11

## Roles

 * MySQL exporter
 * Nginx exporter
 * Apache exporter
 * Node exporter
 * FreeIPA exporter
 * Memcached exporter
 * Redis exporter
 * Postfix exporter

## Example

```
# Node exporter
- hosts: vzguest
  become: yes
  become_method: sudo
  vars:
    node_exporter_version: 1.1.2
    node_exporter_telemetry_address: "{{ ansible_all_ipv4_addresses | ipaddr('10.2.0.0/22') | first }}:9100"
  roles:
    - { role: ./roles/node-exporter }
```
