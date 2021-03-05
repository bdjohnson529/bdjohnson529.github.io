---
title: "Postgres on WSL"
layout: default
parent: SDE
parent_path: /tutorials/software-development/
---
Microsoft offers a detailed guide for installing Postgres on [WSL.](https://docs.microsoft.com/en-us/windows/wsl/tutorials/wsl-database) In addition to the steps listed on the Microsoft website, I found it necessary to complete the following steps.

# Start and Stop Server
The following commands can be used to start and stop the Postgres server, and check the status of the server.
```bash
sudo service postgresql start
sudo service postgresql stop
sudo service postgresql restart
sudo service postgresql status
```


# Edit Authentication Config File
The authentication config file is located at `/etc/postgresql/10/main/pg_hba.conf`, or a similar location. Change the database login from `peer` to `trust`. Specifically, change this line
```bash
local   all             postgres                                peer
```
to this
```bash
local   all             postgres                                md5
```

Reload, and restart the server for the changes to take effec.t
```bash
sudo /etc/init.d/postgresql reload
sudo service postgresql restart
```

## **External Resources**
* [Install Postgres on WSL](https://docs.microsoft.com/en-us/windows/wsl/tutorials/wsl-database)