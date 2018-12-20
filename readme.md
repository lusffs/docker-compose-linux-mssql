# Restore database in Powershell

Run `docker-compose up -d`

If you're having trouble with path-mapping in a windows environment, set the environment variable `export COMPOSE_CONVERT_WINDOWS_PATHS=1`.

Place .bak file in `./database-backup`-folder created from docker.

Run the following to restore the database:

```
docker exec -it mssql /opt/mssql-tools/bin/sqlcmd -S localhost -U SA -P "Admin123!" -Q “RESTORE FILELISTONLY FROM DISK = '/var/backup/BACKUPNAME.bak'”
```
