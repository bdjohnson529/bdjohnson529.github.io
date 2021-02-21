---
title: "Interact with sqlite3 db"
layout: default
parent: Ruby on Rails
parent_path: /tutorials/ruby-on-rails
---
These commands enable you to interact with the sqlite3 database.

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
