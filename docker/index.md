---
title: "Docker"
layout: default
link: "landing"
parent: Docker
parent_path: /docker/
---
Docker generates an image of our app, making it easier to deploy. Tested with Docker installed on WSL2.

<ul>
{% assign topics = site.pages | where: "topic", "docker" | sort: 'order' %}
{%- for page in topics -%}
  <li>
    <a href="{{ page.url | relative_url }}">
      {{ page.title | escape }}
    </a>
  </li>
{%- endfor -%}
</ul>


## External Resources
* [Docker connection refused](https://pythonspeed.com/articles/docker-connection-refused/)