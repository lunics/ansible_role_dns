# Ansible role: DNS

Only tested on Archlinux.

## Usage
Override [defaults](https://github.com/lunics/ansible_role_dns/blob/main/defaults/main.yml)
```yaml
dns_hosts:
  - host: hostname-machine-A
    ip:   "{{ hostvars['hostname-machine-A'].ipv4 }}"     # fetch "ipv4: 192.168.1.1" variable defined in host_vars/hostname_machine_A/network.yml
  - host: hostname-machine-B
    ip:   192.168.1.10

dns_resolvers:
  - name: local
    nameservers:
      - 192.168.1.1
  - name: quad9
    nameservers:
      - 9.9.9.9
      - 149.112.112.112
      - 2620:fe::fe
      - 2620:fe::9

hostname: machine-1        # must always be set or not in host_vars, never in group_vars
```
