---
title: "Postgres on WSL"
layout: default
parent: SDE
parent_path: /tutorials/postgres-wsl/
---
Microsoft offers a detailed guide for installing Postgres on [WSL.](https://docs.microsoft.com/en-us/windows/wsl/tutorials/wsl-database) In addition to the steps listed on the Microsoft website, I found it necessary to complete the following steps.

# Edit Authentication Config File
The authentication config file is located at `/etc/postgresql/10/main/pg_hba.conf`, or a similar location. Change the database login from `peer` to `trust`. Specifically, change this line
```bash
local   all             postgres                                peer
```
to this
```bash
local   all             postgres                                trust
```


## **External Resources**
* [Install Postgres on WSL](https://docs.microsoft.com/en-us/windows/wsl/tutorials/wsl-database)