---
title: "Python"
layout: default
link: "landing"
parent: Python
parent_path: /python/
---
These are my python resources.

{% assign topics = site.pages | where: "link", "python" %}
{%- for page in topics -%}
  <h3>
    <a class="post-link" href="{{ page.url | relative_url }}">
      {{ page.title | escape }}
    </a>
  </h3>
{%- endfor -%}