---
title:  "Project Structure"
layout: default
parent: Flask
parent_path: /tutorials/flask/
---

Flask is an exceptionally flexible web application framework. Other frameworks, such as Ruby on Rails, or Django, impose structure on your projects. The flexibility of Flask is both an asset and a liability - the biggest danger is that with no externally imposed structure, a project can evolve into a complicated mess of code which is impossible to maintain.

The structure of our Flask projects borrows from some software design patterns, including the [Model-view-controller](https://www.sitepoint.com/model-view-controller-mvc-architecture-rails/) pattern and [RESTful APIs](https://www.smashingmagazine.com/2018/01/understanding-using-rest-api/). True to the spirit of Flask, we will apply these design patterns as much as possible, while making exceptions when necessary.

## Templates
Flask uses templates to render HTML pages. As defined in the [Flask documentation](https://flask.palletsprojects.com/en/1.1.x/tutorial/templates/), templates are *files that contain static data as well as placeholders for dynamic data*. The templates folder contains HTML, and Jinja.

We also use the templates folder to save markdown files. Pages with a lot of writing are easy to create in Markdown. Python has a `markdown` module which can easily convert markdown to HTML. A blog post, for example, might have two `templates`
```
blog.md
blog.html
```

In the Python file used to define the route, simply use the `markdown` module to convert to HTML:
```python
import markdown

f = open('App/templates/blog.md', encoding="utf8")
lines = f.read()
f.close()

text = markdown.markdown(lines)
```

And pass the text object to the HTML, using `render_template`
```python
return render_template("blog.html", text=text)
```