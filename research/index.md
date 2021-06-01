---
title: "Research"
layout: default
link: "landing"
parent: Research
parent_path: /research/
---
Notes from my research.

## Medical Research
<ul>
  {% assign topics = site.pages | where: "topic", "medical-research" %}
  {%- for page in topics -%}
  <li>
    <a href="{{ page.url | relative_url }}">{{ page.title | escape }}</a>
  </li>
  {%- endfor -%}
</ul>