# PostgreSqlOnDocker

## Environment

You need to install Docker Desktop or docker, docker compose.

## How to use
1. open Docker Desktop(or run docker by terminal)

2. build
```terminal
$ docker-compose build
```

3. start server in background process.
```terminal
$ docker-compose up -d
```

4. check what this container is running.
```terminal
$ docker-compose ps
NAME                COMMAND                  SERVICE             STATUS              PORTS
sample-db-dev       "docker-entrypoint.s…"   database            running             0.0.0.0:5432->5432/tcp
```

5. login to database.

```terminal
$ docker-compose exec database bash
580677b2bfe0:/# psql -U admin sample
psql (13.10)
Type "help" for help.

sample=#
```

6. create database and dive into created db.

```terminal
sample=# CREATE DATABASE mydb;
CREATE DATABASE

sample=# \c mydb
You are now connected to database "mydb" as user "admin".
```

7. create table and enjoy playing PostgreSQL !

8. If you exit from db and the container, please type \q and exit. Then you can go back to your termial.

```terminal
mydb=# \q
580677b2bfe0:/# exit
exit
```
