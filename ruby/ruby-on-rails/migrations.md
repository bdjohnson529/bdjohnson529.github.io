---
title: "Migrations"
layout: default
topic: ruby-on-rails
order: 0
parent: Ruby
parent_path: /ruby/
---
Migrations are a way to alter the database schema over time.

## ActiveRecord Generator
ActiveRecord generators create migration files. For example, to generate a migration to add a Weight to the Person model,
```bash
bin/rails g migration AddWeightToPeople
```

## Commands

| Command | Description |
| -- | -- |
| db:migrate | runs (single) migrations that have not run yet. |
| db:create | creates the database |
| db:drop | deletes the database |
| db:schema:load | creates tables and columns within the existing database following schema.rb. This will delete existing data. |
| db:setup | does db:create, db:schema:load, db:seed |
| db:reset | does db:drop, db:setup |
| db:migrate:reset | does db:drop, db:create, db:migrate |


## Resources
* [RailsGuides - Active Record Migrations](https://guides.rubyonrails.org/active_record_migrations.html)
* [Stack Overflow](https://stackoverflow.com/a/10302357/9080991)