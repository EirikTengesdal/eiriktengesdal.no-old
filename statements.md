---
layout: homepage
title: Statements
permalink: /statements/
---
<h1 id="statements"></h1>
<h2 style="margin: 40px 0px 10px;">Statements</h2>

<ul>
  {% for statement in site.statements %}
  <li>
    {{ statement.title }}
    {{ content }}
  </li>
  {% endfor %}
</ul>
