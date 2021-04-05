---
layout: default
title: SQL Server
parent: Data Engineering
parent_path: /tutorials/data-engineering
---

These queries are tested in T-SQL on a physical SQL Server.

## Cheat Sheet

Get column names in table:
```sql
SELECT	COLUMN_NAME
FROM	INFORMATION_SCHEMA.COLUMNS
WHERE	TABLE_NAME = 'myTableName'
```