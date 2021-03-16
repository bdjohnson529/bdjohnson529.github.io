---
title:  "Flask databases"
layout: default
parent: Flask
parent_path: /tutorials/flask/
---

Most web applications use a database to store and maintain application data. It's possible to build a Flask app using a collection of files saving application data in the background (this could be a quick way to prototype); however, using a database on the backend is usually a more sustainable solution.

## Sqlite

Sqlite is a lightweight SQL database engine which pairs well with Flask. Sqlite3 is automatically installed with the standard distribution of Python. You can verify the installation of sqlite by entering the following command in the Python console:
```
import sqlite3
```

## Sqlalchemy
The prevailing way to interact with a database, in a web application, is using object-relational-mappers. ORMs empower you to write database queries in a language other than SQL. [SQLAlchemy](https://docs.sqlalchemy.org/en/14/) is a popular ORM tool for Python. [Flask-SQLAlchemy](https://pypi.org/project/Flask-SQLAlchemy/) is a Flask extension which add support for SQLAlchemy to the application. To install:
```bash
pip install Flask-SQLAlchemy
```