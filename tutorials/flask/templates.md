---
title:  "Templates"
layout: default
parent: Flask
parent_path: /tutorials/flask/
---

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