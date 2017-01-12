#hashivault
Installs the HashiCorp Vault binary as a systemd service.

##Requirements
The role was built with Ansible 2.2 and Centos 7, and installs vault as a systemd service.

##Role Variables

```
---
# hashicorp-vault/vars/main.yml

vault_src: https://releases.hashicorp.com/vault/0.6.2/vault_0.6.2_linux_amd64.zip
service_name: Hashi Corp Vault
user_name: vault
group_name: vault
binary_path: /usr/local/bin/vault
data_dir: /var/lib/vault
cfg_path: /etc/vault.cfg
```

The vault_src var points to a particular version of Vault, because there's no simple ~/latest.zip uri.

##Dependencies
None

##Example Playbook
```
---
# vault.yml
- hosts: vaulthost
  roles:
         - { role: hashivault, tags: ['hashivault'] }
```
To install Vault on a node:
```
ansible-playbook -i hosts vault.yml
```

##License
BSD

##Author Information
[thisdougb](https://github.com/thisdougb)
