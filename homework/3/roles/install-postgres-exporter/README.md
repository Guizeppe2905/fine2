# Ansible role: install pg exporter

Install Prometeus Exporter 4 PG

## Role Variables

```yaml
postgresql_exporter_user: postgres
postgresql_exporter_password: qazwsxedc
postgresql_port: 5432
```

## Example Playbook

Call the role with custom pg port:

```yaml
- hosts: servers
  roles:
  - role: install-postgres-exporter
    postgresql_port: 6432
```

## License

Apache Licence 2.0

## Author Information

dR
