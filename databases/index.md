---
title: "Databases"
layout: default
link: "landing"
parent: Databases
parent_path: /databases/
---
Notes from configuring and deploying databases on the Windows Subsystem for Linux.

<ul>
{% assign topics = site.pages | where: "topic", "databases" | sort: 'order' %}
{%- for page in topics -%}
  <li>
    <a href="{{ page.url | relative_url }}">
      {{ page.title | escape }}
    </a>
  </li>
{%- endfor -%}
</ul>