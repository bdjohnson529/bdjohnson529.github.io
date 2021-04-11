---
title: "Javascript"
layout: default
link: "landing"
parent: Javascript
parent_path: /javascript/
---
These are my notes from learning Javascript.

<ul>
{% assign topics = site.pages | where: "link", "javascript" %}
{%- for page in topics -%}
  <li><a href="{{ page.url | relative_url }}">
    {{ page.title | escape }}
  </a></li>
{%- endfor -%}
</ul>