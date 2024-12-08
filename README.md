# Ansible Role for MySQL

[![CircleCI](https://circleci.com/gh/lifeofguenter/ansible-role-mysql/tree/main.svg?style=svg)](https://circleci.com/gh/lifeofguenter/ansible-role-mysql/tree/main)

This ansible role will install MySQL and apply some "sane" production settings.
If munin or fail2ban are installed, additional tasks will run accordingly to
enable them for MySQL as well.

## Requirements

In your `requirements.yml`:

```yaml
collections:
  - name: community.mysql
```

## Role Variables

```
mysql_user: *required*
mysql_password: *required*

mysql_bind_address: 127.0.0.1
mysqlx_bind_address: "{{ mysql_bind_address }}"
mysqlx_disable: true

mysql_charset: utf8mb4
mysql_collation: "{{ mysql_charset }}_0900_ai_ci"
#mysql_collation: "{{ mysql_charset }}_unicode_520_ci"

mysql_innodb_buffer_pool_size: "{{ (ansible_memtotal_mb * 0.5) | round | int }}M"
mysql_innodb_log_file_size: "128M"

mysql_max_connections: 256
mysql_log_error_verbosity: 2
mysql_require_secure_transport: ON

mysql_version: "8.0"
#mysql_version: "5.7"

mysql_databases: []
```

## Dependencies

_none_

## Example Playbook

```
- hosts: servers
  roles:
    - src: lifeofguenter.oracle-mysql
```

## License

[MIT](LICENSE)

## Author Information

Günter Grodotzki <gunter@grodotzki.com>
