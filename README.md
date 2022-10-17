Ansible Role
=========

Ansible role for pushing mariadb/mysql database from the ansible controller to the remote machine
```
ansible-galaxy install abrararshad.mariadb_import
```

Role Variables
--------------

```
mariadb_import_dump_file_path: ''
mariadb_import_remote_dump_folder: '/tmp/dumps'
mariadb_import_database: ''
mariadb_import_user: ''
mariadb_import_password: ''
```

Specify where the location of the SQL file on local machine/ansible controller, it will zip before copying the database

```
mariadb_import_remote_dump_folder: '/tmp/data/sql.dump'
```

Example
----------------

```
---
- name: 'MariaDB psuh'
  hosts: "all"
  roles:
    - name: abrararshad.mariadb_import
      vars:
        mariadb_import_dump_file_path: '/tmp/data/sql.dump'
        mariadb_import_database: "{{ app_mariadb_dbname }}"
        mariadb_import_user: "{{ app_mariadb_dbuser }}"
        mariadb_import_password: "{{ app_mariadb_dbuser_password }}"

```

License
-------

BSD