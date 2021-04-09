---
title: "Ruby"
layout: default
link: "landing"
parent: Ruby
parent_path: /ruby/
---
These are my ruby resources.

{% assign topics = site.pages | where: "link", "ruby" %}
{%- for page in topics -%}
  <h3>
    <a class="post-link" href="{{ page.url | relative_url }}">
      {{ page.title | escape }}
    </a>
  </h3>
{%- endfor -%}