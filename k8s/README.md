# Запуск
- Для начала, нужно запустить `minio`, в нем хранятся бэкапы для постегреса
- После этого, создать `postgres-backups` бакет в `minio`
- Создать и запустить кластер `pg/zalando`
- Запуск `ispn`
- Запуск `kc`

## Backup
Бэкапы снимаются с базы каждый день в 00:30.
Настроить данное поведение можно в `postgresql-operator-default-configuration.yaml` по пути `configuration.logical_backup`

## Улучшения
- Использовать minio operator `https://github.com/minio/operator`