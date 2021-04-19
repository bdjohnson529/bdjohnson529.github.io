---
layout: default
title: SQL Cheat Sheet
topic: databases
order: 3
parent: Databases
parent_path: /databases/
---

These queries are tested in T-SQL on a physical SQL Server.

## Cheat Sheet

Get table schema
```sql
SELECT  table_name,
        column_name,
        data_type
FROM    information_schema.columns
WHERE   table_name = 'mytablename';
```