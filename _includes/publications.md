<h2 id="publications" style="margin: 2px 0px -15px;">Publications</h2>

<div class="publications">
<ol class="bibliography">

{% for link in site.data.publications.main %}

<li>
<div class="pub-row">
  <div class="col-sm-3 abbr" style="position: relative;padding-right: 15px;padding-left: 15px;">
    {% if link.image %} 
    <img src="{{ link.image }}" class="teaser img-fluid z-depth-1" style="width=100;height=40%">
    {% endif %}
    {% if link.journal_short %} 
    <abbr class="badge">{{ link.journal_short }}</abbr>
    {% endif %}
  </div>
  <div class="col-sm-9" style="position: relative;padding-right: 15px;padding-left: 20px;">
      <div class="title year"><a href="{{ link.pdf }}">{{ link.title }}</a>, {{ link.year }}</div>
      <div class="author">{{ link.authors }}</div>
      <div class="journal"><em>{{ link.journal }}</em>
      </div>
    <div class="links">
      {% if link.pdf %}
      <a href="{{ link.pdf }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;"><i class="far fa-file-pdf"></i> PDF</a>
      {% endif %}
      {% if link.url %} 
      <a href="{{ link.url }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;"><i class="fa fa-link"></i> URL</a>
      {% endif %}
      {% if link.duo %}
      <a href="{{ link.duo }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;"><i class="fa fa-database"></i> DUO Archive</a>
      {% endif %}
      {% if link.doi %} 
      <a href="{{ link.doi }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;"><i class="ai ai-doi"></i> DOI</a>
      {% endif %}
      {% if link.anthology %} 
      <a href="{{ link.anthology }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;"><i class="fa fa-book"></i> Anthology URL</a>
      {% endif %}
      {% if link.code %} 
      <a href="{{ link.code }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">Code</a>
      {% endif %}
      {% if link.page %} 
      <a href="{{ link.page }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;"><i class="fa fa-link"></i> Project Page</a>
      {% endif %}
      {% if link.bibtex %}
      <a href="{{ link.bibtex }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;"><img src=".assets/img/2560px-BibTeX_logo.svg.png" style="width: 20px; height: 6.45px;"></a>
      {% endif %}
      {% if link.notes %} 
      <strong> <i style="color:#e74d3c">{{ link.notes }}</i></strong>
      {% endif %}
      {% if link.others %} 
      {{ link.others }}
      {% endif %}
    </div>
  </div>
</div>
</li>

<br>

{% endfor %}

</ol>
</div>

