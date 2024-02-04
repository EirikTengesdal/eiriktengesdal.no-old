<h2 id="publications" style="margin: 2px 0px -15px;">Publications</h2>

<script src="https://cdn.jsdelivr.net/clipboard.js/1.5.12/clipboard.min.js"></script>
<script>new Clipboard('.copy_btn');</script>

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
      <!-- Button trigger modal -->
      <a href="#" class="btn btn-sm z-depth-0" role="button" style="font-size:12px;" data-toggle="modal" data-target="#bibtexModal"><i class="icon-BibTeX"></i> BibTeX</a>
      <!-- Modal -->
      <div class="modal fade" id="bibtexModal" tabindex="-1" role="dialog" aria-labelledby="bibtexModalLabel" aria-hidden="true">
        <div class="modal-dialog" role="document">
          <div class="modal-content">
            <div class="modal-header">
              <h5 class="modal-title" id="bibtexModalLabel">BibTeX Code</h5>
              <button type="button" class="close" data-dismiss="modal" aria-label="Close">
                <span aria-hidden="true">&times;</span>
              </button>
            </div>
            <div class="modal-body">
              <pre id="bibtexCode">{{ link.bibtex }}</pre>
            </div>
            <div class="modal-footer">
              <button type="button" class="btn btn-secondary" data-dismiss="modal">Close</button>
              <button type="button" class="btn btn-primary copy_btn" data-clipboard-target="#bibtexCode">
                Copy to Clipboard
              </button>
            </div>
          </div>
        </div>
      </div>
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

