# Ansible role: install pg

Install PG 4 Linux

## Role Variables

```yaml
---
postgresql_data_directory: /data/postgres/data
postgresql_pg_hba_conf_auth_records:
  - name: Всем всё внутри 10й локалки.
    host: host
    db: all
    user: all
    address: 10.0.0.0/8
    auth_method: md5
  - name: Разрешаем управление через сокет
    host: local
    db: all
    user: all
    address: trust
    auth_method:

password_for_default_postgres_user: qazwsxedc
postgres_db_login_host: "{{ inventory_hostname }}"
postgres_db_login_port: 5432
postgres_db_login_user: postgres
postgres_db_login_password: "{{ password_for_default_postgres_user }}"

postgresql_systemd_override_dir: "/etc/systemd/system/postgresql@{{ postgresql_latest_version_fact }}-main.service.d"
```

## Example Playbook

Call the role with custom dba password:

```yaml
- hosts: servers
  roles:
  - role: install-postgresql
    password_for_default_postgres_user: 11311131
```

## License

Apache Licence 2.0

## Author Information

dR
