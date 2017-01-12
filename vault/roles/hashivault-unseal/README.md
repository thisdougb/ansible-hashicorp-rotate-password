#hashivault-unseal
Unseals an existing HashiCorp Vault via http API calls.

This role was built for dev and test purposes, and is partnered with the hashivault-init role.

##Requirements
The keys to unseal the vault must exist in the roles dir, and are created with the hashivault-init role.

##Role Variables
No standard format Ansible variables, however this role use vault key data.

```
- name: retrieve keys locally
  set_fact:
    vault_keys: "{{ lookup('file','{{ role_path }}/../.hashicorp_vault_keys.json') | from_json }}"
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
         - { role: hashivault-unseal, tags: ['hashivault-unseal'] }
```
To initialise Vault on a node:
```
ansible-playbook -i hosts vault.yml
```

##License
BSD

##Author Information
[thisdougb](https://github.com/thisdougb)
