# Stackoverflow Database Dumps

Stackoverflow dumps are created from the Stackoverflow archives.

## Source

See https://www.brentozar.com/archive/2018/01/updated-and-smaller-stack-overflow-demo-databases/

- Stackoverflow archives: https://archive.org/download/stackexchange
- Tool to convert archives into sql dump: https://github.com/BrentOzarULTD/soddi

## Import

1. Copy the StackOverflow2010.mdf and StackOverflow2010_log.ldf files to docker

```sh
> docker cp StackOverflow2010.mdf sql1:/mnt/data
> docker cp StackOverflow2010_log.ldf sql1:/mnt/data

# Make the files writable
> docker exec -it -u 0 bash
    container> chmod a+rw /mnt/data/StackOverflow2010*
```

2. Attach the files to a new database

```sql
IF NOT EXISTS (
    SELECT [name]
            FROM sys.databases
	    WHERE [name] = N'StackOverflow2010'
)
CREATE DATABASE StackOverflow2010
ON (FILENAME=N'/mnt/data/StackOverflow2010.mdf')
LOG ON (FILENAME=N'/mnt/data/StackOverflow2010_log.ldf')
FOR ATTACH;
GO
```

## Schema Notes

See https://www.brentozar.com/archive/2018/02/gentle-introduction-stack-overflow-schema/
