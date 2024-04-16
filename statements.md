---
layout: homepage
title: Statements
---
<h1 id="statements"></h1>
<h2 style="margin: 40px 0px 10px;">Statements</h2>

{% for statement in site.statements %}
  {{ statement }} <br>
{% endfor %}
