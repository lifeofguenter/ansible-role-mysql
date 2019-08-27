[![Build Status](https://travis-ci.org/lifeofguenter/ansible-role-oracle-mysql.svg?branch=master)](https://travis-ci.org/lifeofguenter/ansible-role-oracle-mysql)

# Ansible Role for MySQL (Oracle)

This ansible role will install MySQL (Oracle) and apply some "sane" production settings.
If munin and/or fail2ban are installed, additional tasks will run accordingly to activate them for MySQL as well.

## Requirements

_none_

## Role Variables

```
mysql_user: *required*

mysql_password: *required*

mysql_bind_address: 0.0.0.0

mysql_charset: utf8mb4

mysql_collation: "{{ mysql_charset }}_unicode_ci"

mysql_datadir: /var/lib/mysql

mysql_max_connections: 256

mysql_innodb_buffer_pool_size: "{{ (ansible_memtotal_mb * 0.5) | round | int }}M"

mysql_innodb_lock_wait_timeout: 50

mysql_innodb_log_file_size: "128M"

mysql_log_error_verbosity: 2

mysql_require_secure_transport: On
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
