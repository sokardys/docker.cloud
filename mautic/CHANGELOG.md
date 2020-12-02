# CHANGELOG

## Migrate to v3

### Changed

A few changes has been made to the `docker-compose.template.yaml` & the _docker-compose_ version has been upgraded to `3.6`

#### MAUTIC SERVICE

##### New env vars

```yaml
MAUTIC_DB_USER: root
MAUTIC_DB_NAME: mautic3
MYSQL_PORT_3306_TCP: 3306
MAUTIC_RUN_CRON_JOBS: 'true'
```

##### Remove env vars
```yaml
MAUTIC_TRUSTED_PROXIES: 0.0.0.0/0
```

#### MYSQL SERVICE

##### New image used

```yaml
image: powertic/percona-docker
```

##### New startup command

```yaml
command: --character-set-server=utf8mb4 --collation-server=utf8mb4_general_ci --sql-mode=""
```
