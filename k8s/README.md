# Запуск
- Для начала, нужно запустить `minio`, в нем хранятся бэкапы для постегреса
- После этого, создать `postgres-backups` бакет в `minio`
- Создать и запустить кластер `pg/zalando`
- Запуск `ispn`
- Запуск `kc`

## Backup
Бэкапы снимаются с базы каждый день в 00:30.
Настроить данное поведение можно в `pg-conf.yaml` по пути `configuration.logical_backup`

### Запустить бэкап вручную
```shell
kubectl get cronjobs
```

```shell
kubectl create job --from=cronjob/logical-backup-min manual-backup
```

```shell
kubectl logs -l job-name=manual-backup
```

```shell
kubectl get events --sort-by=.metadata.creationTimestamp
```


## Улучшения
- Использовать minio operator для прода  `https://github.com/minio/operator`

