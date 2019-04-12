# egeneralov.hypervisor

Ensure target have hypervisor power

## Requirements

Debian 9.

## Role Variables

    disk_pool:
      name: default
      directory: /var/lib/libvirt/default
    
    net_pool:
      name: default
      address: 192.168.122.1/24
      uuid: "{{ ansible_default_ipv4.macaddress | to_uuid }}"
    
    pkg:
      Debian:
        stretch:
          - qemu-kvm
          - genisoimage
          - libvirt-clients
          - qemu-utils
          - libvirt-daemon-system
          - virtinst
          - python-pip
          - libosinfo-bin
    
    pip:
      - lxml
      - libvirt-python

## Example Playbook

    - hosts: servers
      remote_user: root
      roles:
        - egeneralov.hypervisor

## License

MIT

## Author Information

Eduard Generalov <eduard@generalov.net>
