---
title: "Interact with sqlite3 db"
layout: default
parent: Ruby on Rails
parent_path: /tutorials/ruby-on-rails
---
These commands enable you to interact with the sqlite3 database, if you have configured rails to run with sqlite3 in the backend. The sqlite3 database might be stored in `db/development.sqlite3`, for example. To access this file:
```bash
sqlite3 db/development.sqlite3
```

## Commands
Select all tables
```bash
.tables
```

List schema for TABLE
```bash
.schema TABLE
```