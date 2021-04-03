---
title: "Postgres"
layout: default
parent: Databases
parent_path: /tutorials/databases/
---
PostgreSQL is a powerful relational database. Relational databases offer a wealth of performance advantages over file-based data storage.

# Cheat Sheet
Show all tables
```bash
user-# \dt
```

Quit CLI
```bash
user-# \q
```

# Start and Stop Server
The following commands can be used to start and stop the Postgres server, and check the status of the server.
```bash
sudo service postgresql start
sudo service postgresql stop
sudo service postgresql restart
sudo service postgresql status
```

# CLI Log In
```bash
psql -d mydb -U myuser
```
Root login
```bash
psql -U postgres
```

## Installation on WSL
Microsoft offers a detailed guide for installing Postgres on [WSL.](https://docs.microsoft.com/en-us/windows/wsl/tutorials/wsl-database) In addition to the steps listed on the Microsoft website, I found it necessary to complete the following steps.

The authentication config file is located at `/etc/postgresql/10/main/pg_hba.conf`, or a similar location. Change the authentication method from `peer` to `trust`. Specifically, I changed these two lines
```bash
local   all             postgres                                peer
local   all             all                                     peer
```
to these:
```bash
local   all             postgres                                trust
local   all             all                                     trust
```

Reload, and restart the server for the changes to take effect.
```bash
sudo /etc/init.d/postgresql reload
sudo service postgresql restart
```


## **External Resources**
* [Install Postgres on WSL](https://docs.microsoft.com/en-us/windows/wsl/tutorials/wsl-database)