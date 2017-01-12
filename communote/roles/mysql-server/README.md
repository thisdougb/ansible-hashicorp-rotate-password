## mysql-server

Install mysql 5.7 and set a randomly generated password, store this password in Vault.

## Requirements

A HashiCorp Vault instance, with a generic backend writeable by the root_token being used.

## Role Variables

For simplicity the mysql repo is stored locally and access via this variable.

```
# roles/mysql-server/vars/main.yml 
mysql_repo_rpm: mysql57-community-release-el7-9.noarch.rpm
```

## Dependencies

n/a

## Example Playbook

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```
---
- hosts: communote-be-db

  roles:
    - { role: mysql-server, tags: ['mysql-server'] }
```

## License

BSD

## Author Information

[thisdougb](https://github.com/thisdougb)
