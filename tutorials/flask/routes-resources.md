---
title:  "Routes and Resources"
layout: default
parent: Flask
parent_path: /tutorials/flask/
---

Routing is the mechanism by which HTTP requests are routed to the code which handles them. When a user visits the page `/home`, their computer makes an HTTP request to the server. Routing will determine what happens from there.

In Flask, routes are defined using decorators. The following route would return the string `hello world` to the client computer.

```python
@app.route("/")
def homepage():
    return "hello world"
```

When building an app, a good first step is to map out all of the possible HTTP requests. The most common kind of request is a `GET` request - for example, accessing a homepage might be a `GET` request. Likely you will have some combination of `GET` and `PUT` requests. Each of these requests needs to be mapped to a Python function  using the Flask `route` decorator.
```
GET 	/home
GET 	/people
PUT 	/people
GET 	/people/<:id>
```

Requests can be organized by *resource*. In theory, each resource would have four routes for each of the [CRUD operations](https://en.wikipedia.org/wiki/Create,_read,_update_and_delete) for persistent storage. In practice, you might not need an *update* operation for one of your resources. In the example above, *people* is one resource. All of the routes associcated with this resource could be grouped into one file, `people.py`.

As your project grows, so will your resources. One way to keep track of your routes is to separate the routes by resource, creating a different file with the routes for each resource.
```bash
├── routes
|	├── home.py
|	├── people.py
|	├── pets.py
```

Flask leaves it up to us to stitch all of our code together. How do you combine all of the routes, and the application itself? 

# Implementation
It is helpful to define a single file which the web server interacts with when hosting the app. I usually name the app entry point `wsgi.py`.
```python
from App import init_app

app = init_app()
if __name__ == "__main__":
    app.run(host="0.0.0.0", port=9000)
```
The app entry point imports the `init_app()` function from `App/__init__.py`. The Flask app is instantiated entirely within this function, and returns an `app` object which is `run` by the app entry point.

In the function `init_app()`, we define how our application comes together. We also instantiate the `app` object in this file. In each of the `routes` files, we will import `app` so that we can attach a route.
```python
from flask import current_app as app
```

In the runtime function `init_app`, we must import the routes after `app` has been created. This means we will need to do some un-Pythonic imports in the middle of a function:
```python
def init_app():
    app = Flask(__name__, instance_relative_config=False)
    with app.app_context():
        from .routes import home
        from .routes import people
        from .routes import pets
```

Voila! Now the routes are attached to the app! Separating routes by resource has helped me to make my projects easier to maintain, and understand.