---
title: "Python"
layout: default
link: "landing"
parent: Python
parent_path: /python/
---
These are my python resources.


## Python for Beginnners
<ul>
{% assign topics = site.pages | where: "topic", "introduction" | sort: 'order' %}
{%- for page in topics -%}
  <li>
    <a href="{{ page.url | relative_url }}">
      {{ page.title | escape }}
    </a>
  </li>
{%- endfor -%}
</ul>

## Data Engineering
<ul>
{% assign topics = site.pages | where: "topic", "data-engineering" | sort: 'order' %}
{%- for page in topics -%}
  <li>
    <a href="{{ page.url | relative_url }}">
      {{ page.title | escape }}
    </a>
  </li>
{%- endfor -%}
</ul>

## Flask
<ul>
{% assign topics = site.pages | where: "topic", "flask" | sort: 'order' %}
{%- for page in topics -%}
  <li>
    <a href="{{ page.url | relative_url }}">
      {{ page.title | escape }}
    </a>
  </li>
{%- endfor -%}
</ul>