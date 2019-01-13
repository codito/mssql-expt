# AdventureWorks Sample Database

Adventure Works is sample database for SQL Server.

## Source

- Get backup file from <https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks>
- Copy it to docker container
```sh
> docker cp ~/Downloads/AdventureWorks2017.bak sql1:/var/opt/mssql/data
```
- Restore from Azure Data Studio tool using [instructions](https://docs.microsoft.com/en-us/sql/azure-data-studio/tutorial-backup-restore-sql-server?view=sql-server-2017#restore-a-database-from-a-backup-file)