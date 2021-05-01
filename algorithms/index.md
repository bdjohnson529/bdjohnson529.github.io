---
title: "Algorithms"
layout: default
link: "landing"
parent: Algorithms
parent_path: /algorithms/
---
Common algorithms for learning and practicing computer science.

## Concepts
<ul>
{% assign topics = site.pages | where: "topic", "algorithm-concepts" | sort: 'order' %}
{%- for page in topics -%}
  <li>
    <a href="{{ page.url | relative_url }}">
      {{ page.title | escape }}
    </a>
  </li>
{%- endfor -%}
</ul>

## Problems
<ul>
{% assign topics = site.pages | where: "topic", "algorithm-problems" | sort: 'order' %}
{%- for page in topics -%}
  <li>
    <a href="{{ page.url | relative_url }}">
      {{ page.title | escape }}
    </a>
  </li>
{%- endfor -%}
</ul>