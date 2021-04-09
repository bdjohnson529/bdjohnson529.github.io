---
title: "Databases"
layout: default
link: "landing"
parent: Databases
parent_path: /databases/
---
Notes from configuring and deploying databases on the Windows Subsystem for Linux.

* [SQL Server](sql-server.html)
* [sqlite3 db](sqlite.html)
* [postgres](postgres.html)


{%- for page in topics -%}
  <ul>
    <li>
      <a class="post-link" href="{{ page.url | relative_url }}">
        {{ page.title | escape }}
      </a>
    </li>
  </ul>
{%- endfor -%}