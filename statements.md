---
layout: homepage
title: Statements
permalink: /statements/
---
<h1 id="statements"></h1>
<h2 style="margin: 40px 0px 10px;">Hearing statements</h2>
This page contains response statements to public consultations for comments  (_høringer_).

{% for statement in site.statements %}
  - <a href="#{{ statement.id }}">{{ statement.title | markdownify | remove: "<p>" | remove: "</p>" }}</a>
{% endfor %}

{% for statement in site.statements %}
  <h3 id="{{ statement.id }}"> {{ statement.title | markdownify }}</h3>
  {{ statement.content | markdownify }}
  PDF copy {{ statement.pdfcomment }}: <a href="{{ statement.data }}" title="{{ PDF }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:120%;"><i class="far fa-file-pdf"></i></a>
  <object data="{{ statement.data }}" width="100%" height="900" type='application/pdf'></object>
{% endfor %}