# Ansible Role - Tinc mesh VPN

Provisions Tinc VPN in mesh topology (i.e. where every machine is connected to each other). It ensures that:
- Tinc server is installed on all cluster nodes
- SSH keys are generated on each machines and propagated to all the other machines
- Tinc systemd service is installed and enabled

Kudos for [@thisismitch](https://github.com/thisismitch) for creating [ansible-tinc](https://github.com/thisismitch/ansible-tinc)
which was an inspiration for creating this role.

## Compatibility

This playbook has been tested against Fedora 28.

## Installation 

    ansible-galaxy install hekonsek.tinc-mesh,0.0

## Example playbook

```
- hosts: tinc-mesh-test
  roles:
    - { role: ../ansible-tinc-mesh }
```

## Example inventory file

```
[tinc-mesh-test]
machine001 vpn_ip=172.22.1.1 ansible_host=212.47.228.98
machine002 vpn_ip=172.22.1.2 ansible_host=51.15.196.248
machine003 vpn_ip=172.22.1.3 ansible_host=51.16.180.143
```

## License

Apache 2.0