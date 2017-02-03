# Backup de volumes

## Référence

https://docs.docker.com/engine/tutorials/dockervolumes/#/backup-restore-or-migrate-data-volumes

## Génération du backup

```
docker run --rm --volumes-from dbstore -v $(pwd):/backup ubuntu tar cvf /backup/backup.tar /dbdata
```

## Restore de backup

### Conteneur que l'ont veut backuper.

```
docker run -v /dbdata --name dbstore2 ubuntu /bin/bash
```

### Lancement d'un conteneur temporaire pour restaurer les données.

```
docker run --rm --volumes-from dbstore2 -v $(pwd):/backup ubuntu bash -c "cd /dbdata && tar xvf /backup/backup.tar --strip 1"
```