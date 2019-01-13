# mssql-expt
Experiments with SQL Server on Linux

## Setup

Gets the docker image for SQL Server and connects to it from a command line
client.

```sh
> docker pull mcr.microsoft.com/mssql/server:2017-latest
> docker run -e 'ACCEPT_EULA=Y' -e 'SA_PASSWORD=Passw0rd' -p 1433:1433 --name sql1 -d mcr.microsoft.com/mssql/server:2017-latest
```

Enumerate default databases in SQL server.
```sh
> docker exec sql1 /opt/mssql-tools/bin/sqlcmd -S localhost -U SA -P 'Passw0rd' -q 'select name from sys.databases'

name
--------------------------------------------------------------------------------------------------------------------------------
master
tempdb
model
msdb

(4 rows affected)

Sqlcmd: Warning: The last operation was terminated because the user pressed CTRL+C.
```

## Azure data studio

Cross platform database management tool. Highly recommended.
Install from <https://github.com/Microsoft/azuredatastudio>.
