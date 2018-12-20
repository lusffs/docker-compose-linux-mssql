# Retore database in Powershell

run `docker-compose up -d`

Place .bak file in `./database-backup`-folder created from docker.

Run the following to restore the database:

```
docker exec -it mssql /opt/mssql-tools/bin/sqlcmd -S localhost -U SA -P "Admin123!" -Q “RESTORE FILELISTONLY FROM DISK = '/var/backup/BACKUPNAME.bak'”
```
