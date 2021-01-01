Ansible Role: Percona XtraBackup
================================

[![Build Status](https://img.shields.io/travis/com/webplates/ansible-role-xtrabackup.svg?style=flat-square)](https://travis-ci.com/webplates/ansible-role-xtrabackup)
[![Ansible Galaxy](http://img.shields.io/badge/galaxy-webplates.xtrabackup-5fb7b9.svg?style=flat-square)](https://galaxy.ansible.com/webplates/xtrabackup)

Installs [Percona XtraBackup](https://www.percona.com/software/mysql-database/xtrabackup).

**Note:** For now only MySQL 8 is supported.

Role Variables
--------------

| Variable | Default | Description |
| -------- | ------- | ----------- |
| `xtrabackup_create_mysql_user` | `false` | Create a MySQL user for XtraBackup |
| `xtrabackup_mysql_user_name` | `bkpuser` | MySQL backup user name |
| `xtrabackup_mysql_user_password` | *none* | MySQL backup user password (required when `create_mysql_backup_user` is `true`) |
| `xtrabackup_mysql_grants` | `[ BACKUP_ADMIN, PROCESS, RELOAD, LOCK TABLES, REPLICATION CLIENT ]` | List of grants to apply to the MySQL backup user | 
| `xtrabackup_create_system_user` | `false` | ... |
| `xtrabackup_system_user_name` | `xtrabackup` | ... |

Dependencies
------------

This role does not install MySQL nor configures XtraBackup for running.
Configuration will probably come in future versions.

`xtrabackup` works best with MySQL and Percona-Server. [MariaDB is not supported.](https://mariadb.com/kb/en/mariabackup-overview/#differences-compared-to-percona-xtrabackup)

Example Playbook
----------------

    - hosts: servers
      roles:
         - { role: xtrabackup }

When installing from [Ansible Galaxy](https://galaxy.ansible.com):

    - hosts: servers
      roles:
         - { role: webplates.xtrabackup }

License
-------

MIT
