[![Build Status](https://travis-ci.org/lifeofguenter/ansible-role-oracle-mysql.svg?branch=master)](https://travis-ci.org/lifeofguenter/ansible-role-oracle-mysql)

# Ansible Role for MySQL (Oracle)

This ansible role will install MySQL (Oracle) and apply some "sane" production settings.
If munin and/or fail2ban are installed, additional tasks will run accordingly to activate them for MySQL as well.

## Requirements

_none_

## Role Variables

```
mysql_user: admin
```

```
mysql_password: a-secure-password
```

## Dependencies

_none_

## Example Playbook

```
- hosts: servers
  roles:
    - { role: lifeofguenter.oracle-mysql }
```

## License

MIT

## Author Information

Gunter Grodotzki <gunter@grodotzki.co.za>
