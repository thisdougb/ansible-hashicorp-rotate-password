#hashivault-init
Initialises (resets!) a HashiCorp Vault via http API calls, and stores the keys within the roles dir on the Ansible host.   If you have a vault with existing data this role will wipe it.    If you just want to unseal an existing vault then use the hashivault-unseal role.

This role was built for dev and test purposes, and is partnered with the hashivault-unseal role.

##Requirements
None

##Role Variables
No standard format Ansible variables, however this role saves vault key data locally.

```
- name: save keys locally
  copy:
    content: "{{ vault_init.json }}"
    dest: "{{ role_path }}/../.hashicorp_vault_keys.json"
  delegate_to: localhost
```

##Dependencies
None

##Example Playbook
```
---
# vault.yml
- hosts: vaulthost
  roles:
         - { role: hashivault-init, tags: ['hashivault-init'] }
```
To initialise Vault on a node:
```
ansible-playbook -i hosts vault.yml
```

##License
BSD

##Author Information
[thisdougb](https://github.com/thisdougb)
