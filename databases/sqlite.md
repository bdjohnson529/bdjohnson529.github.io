---
title: "sqlite3 db"
layout: default
parent: Databases
parent_path: /databases/
---
sqlite is a lightweight database, perfect for developing self-contained web applications. If you don't have much data, and you don't need to access your data outside of your application, sqlite is a great choice. This rules out the majority of use cases, but sqlite is also great for developing an application, as it is a file-based database. The host computer does not need to be configured because sqlite stores data the same way Linux does - as files.


## Commands
Enter dbconsole
```bash
rails dbconsole
```

Select all tables
```bash
.tables
```

List schema for TABLE
```bash
.schema TABLE
```


## Resetting the database
Reset entire database
```
rails db:reset
```

Which is equivalent to these commands
```
rails db:drop
rails db:migrate
rails db:seed
```
