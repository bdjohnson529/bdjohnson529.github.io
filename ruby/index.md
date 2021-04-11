---
title: "Ruby"
layout: default
link: "landing"
parent: Ruby
parent_path: /ruby/
---
These are my Ruby resources. I run Ruby on Ubuntu, typically 16.04 or 18.04.

## Installation
<ul>
  {% assign topics = site.pages | where: "topic", "ruby-installation" %}
  {%- for page in topics -%}
  <li>
    <a href="{{ page.url | relative_url }}">{{ page.title | escape }}</a>
  </li>
  {%- endfor -%}
</ul>


## Ruby on Rails
Tested on Rails v6.1.3, using Ruby v2.6.7.

<ul>
{% assign topics = site.pages | where: "topic", "ruby-on-rails" | sort: 'order' %}
{%- for page in topics -%}
  <li>
    <a href="{{ page.url | relative_url }}">
      {{ page.title | escape }}
    </a>
  </li>
{%- endfor -%}
</ul>