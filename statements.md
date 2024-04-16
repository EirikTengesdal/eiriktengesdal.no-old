---
layout: homepage
title: Statements
permalink: /statements/
---
<h1 id="statements"></h1>
<h2 style="margin: 40px 0px 10px;">Statements</h2>

{% for statement in site.statements %}
  <p>{{ statement.content | markdownify }}</p>
{% endfor %}
