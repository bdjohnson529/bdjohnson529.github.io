---
title:  "Flask-SQLAlchemy"
layout: default
parent: Flask
parent_path: /tutorials/flask/
---

Most web applications use a database to store and maintain application data. It's possible to build a Flask app using a collection of files saving application data in the background (this could be a quick way to prototype); however, using a database on the backend is usually a more sustainable solution.

The prevailing way to interact with a database, in a web application, is using object-relational-mappers. ORMs empower you to write database queries in a language other than SQL. [SQLAlchemy](https://docs.sqlalchemy.org/en/14/) is a popular ORM tool for Python. [Flask-SQLAlchemy](https://pypi.org/project/Flask-SQLAlchemy/) is a Flask extension which add support for SQLAlchemy to the application. To install:
```bash
pip install Flask-SQLAlchemy
```

# Models
Flask-SQLAlchemy [declares models](https://flask-sqlalchemy.palletsprojects.com/en/2.x/models/) - Python objects which are saved in the database. For example, you could declare a model for a Person, which contains a single attribute (a name).
```python
class Scenario(db.Model):
    id = db.Column(db.Integer, primary_key=True)
    name = db.Column(db.String(80), unique=True, nullable=False)

    def __repr__(self):
        return '<Name %r>' % self.name
```

To add this model to the database, add some code to the application entry point.