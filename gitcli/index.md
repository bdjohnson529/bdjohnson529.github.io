---
title: "Git CLI"
layout: default
link: "landing"
excerpt: "Command line Git cheat-sheets."
parent: Git CLI
parent_path: /gitcli/
---
Git is version control software which manages changes to files. These resources document usage of Git with the command line.

* [Git Commands](git-commands.html)


# Workflows
<ul>
{% assign topics = site.pages | where: "topic", "git-workflow" | sort: 'order' %}
{%- for page in topics -%}
  <li>
    <a href="{{ page.url | relative_url }}">
      {{ page.title | escape }}
    </a>
  </li>
{%- endfor -%}
</ul>