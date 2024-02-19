<h2 id="publications" style="margin: 40px 0px 10px;">Publications</h2>
For a more extensive overview, view my <a href="{{ site.cristin }}" title="{{ site.cristin }}" rel="noopener">Cristin profile</a>.
<div class="publications">
<ol class="bibliography">
{% for link in site.data.publications.main %}
<li>
<div class="pub-row">
  <div class="col-sm-3 abbr" style="position: relative; padding-right: 15px; padding-left: 15px;">
    {% if link.image %} 
    <img src="{{ link.image }}" class="teaser img-fluid z-depth-1" style="width:100; height:100%">
    {% endif %}
    {% if link.journal_short %} 
    <abbr class="badge">{{ link.journal_short }}</abbr>
    {% endif %}
  </div>
  <div class="col-sm-9" style="position: relative; padding-right: 15px; padding-left: 20px;">
      <div class="title year"><a href="{{ link.pdf }}" title="{{ link.pdf }}" rel="noopener">{{ link.title }}</a>, {{ link.year }}</div>
      <div class="author">{{ link.authors }}</div>
      <div class="journal"><em>{{ link.journal }}</em>
      </div>
    <div class="links">
      {% if link.pdf %}
      <a href="{{ link.pdf }}" title="{{ link.pdf }}" rel="noopener" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;"><i class="far fa-file-pdf"></i> PDF</a>
      {% endif %}
      {% if link.url %} 
      <a href="{{ link.url }}" title="{{ link.url }}" rel="noopener" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;"><i class="fa fa-link"></i> URL</a>
      {% endif %}
      {% if link.duo %}
      <a href="{{ link.duo }}" title="{{ link.duo }}" rel="noopener" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;"><i class="fa fa-database"></i> DUO Archive</a>
      {% endif %}
      {% if link.doi %} 
      <a href="{{ link.doi }}" title="{{ link.doi }}" rel="noopener" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;"><i class="ai ai-doi"></i> DOI</a>
      {% endif %}
      {% if link.anthology %} 
      <a href="{{ link.anthology }}" title="{{ link.anthology }}" rel="noopener" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;"><i class="fa fa-book"></i> Anthology URL</a>
      {% endif %}
      {% if link.code %} 
      <a href="{{ link.code }}" title="{{ link.code }}" rel="noopener" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;"><i class="fab fa-github"></i> Code</a>
      {% endif %}
      {% if link.page %} 
      <a href="{{ link.page }}" title="{{ link.page }}" rel="noopener" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;"><i class="fa fa-link"></i> Project Page</a>
      {% endif %}
      {% if link.bibtex %}
      <a href="{{ link.bibtex }}" title="{{ link.bibtex }}" rel="noopener" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;"><i class="icon-BibTeX"></i> BibTeX</a>
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