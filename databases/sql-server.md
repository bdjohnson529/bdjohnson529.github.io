---
layout: default
title: SQL Server
parent: Databases
parent_path: /databases/
---

These queries are tested in T-SQL on a physical SQL Server.

## Cheat Sheet

Get column names in table:
```sql
SELECT	COLUMN_NAME
FROM	INFORMATION_SCHEMA.COLUMNS
WHERE	TABLE_NAME = 'myTableName'
```