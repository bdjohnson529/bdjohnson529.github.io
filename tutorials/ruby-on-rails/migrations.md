---
title: "Migrations"
layout: default
parent: Ruby on Rails
parent_path: /tutorials/ruby-on-rails
---

| Command | Description |
| -- | -- |
| db:migrate | runs (single) migrations that have not run yet. |
| db:create | creates the database |
| db:drop | deletes the database |
| db:schema:load | creates tables and columns within the existing database following schema.rb. This will delete existing data. |
| db:setup | does db:create, db:schema:load, db:seed |
| db:reset | does db:drop, db:setup |
| db:migrate:reset | does db:drop, db:create, db:migrate |

Taken from [Stack Overflow](https://stackoverflow.com/a/10302357/9080991)