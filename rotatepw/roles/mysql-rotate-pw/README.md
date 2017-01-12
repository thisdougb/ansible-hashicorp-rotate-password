mysql-rotate-pw
=========

Rotates the password of mysql's root@localhost user, storing the new password in HashiCorp Vault.

Requirements
------------

Requires the partner role mysql-server to have stored the password in vault.   To avoid further dependencies I pass the password to login to mysql (-pPassword) on the command line, rather than using the mysql_user or expect Ansible modules.

Role Variables
--------------

The root_token group var is needed to access the vault.

Dependencies
------------

A HashiCorp Vault instance, with a generic backend writeable by the root_token being used.

Example Playbook
----------------

```
---
- hosts: communote-be-db

  roles:
    - { role: mysql-rotate-pw, tags: ['mysql-rotate-pw'] }
```

License
-------

BSD

Author Information
------------------

[thisdougb](https://github.com/thisdougb)
