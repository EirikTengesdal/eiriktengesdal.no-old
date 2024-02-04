<h2 id="publications" style="margin: 2px 0px -15px;">Publications</h2>

<script>
    // var clipboard = new ClipboardJS('.copy_btn');

    // clipboard.on('success', function (e) {
    //     setTimeout(function() {
    //         e.clearSelection(); 
    //     }, 80);
    // });
    // clipboard.on('error', function(e) {
    //     setTooltip('Failed!');
    //     hideTooltip();
    // });

    var clipboard = new ClipboardJS('.copy_btn');

    var btns = document.querySelectorAll('.copy_btn');
    for (var i = 0; i < btns.length; i++) {
        btns[i].addEventListener('mouseleave', function(e) {
            e.currentTarget.setAttribute('class', 'copy_btn');
            e.currentTarget.removeAttribute('aria-label');
        });
    }
    clipboard.on('success', function(e) {
        // console.info('Action:', e.action);
        // console.info('Text:', e.text);
        // console.info('Trigger:', e.trigger);
        showTooltip(e.trigger,'Copied!');
        e.clearSelection();
    });

    clipboard.on('error', function(e) {
        // console.error('Action:', e.action);
        // console.error('Trigger:', e.trigger);
        showTooltip(e.trigger,fallbackMessage(e.action));
    });
    function showTooltip(elem, msg) {
        elem.setAttribute('class', 'copy_btn tooltipped tooltipped-s');
        elem.setAttribute('aria-label', msg);
    }
    function fallbackMessage(action) {
        var actionMsg = '';
        var actionKey = (action === 'cut' ? 'X' : 'C');
        if (/iPhone|iPad/i.test(navigator.userAgent)) {
            actionMsg = 'No support :(';
        } else if (/Mac/i.test(navigator.userAgent)) {
            actionMsg = 'Press ⌘-' + actionKey + ' to ' + action;
        } else {
            actionMsg = 'Press Ctrl-' + actionKey + ' to ' + action;
        }
        return actionMsg;
    }
</script>

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
      <p class="links"><label for="BibTeX_{{ link.bibtex }}"><a class="btn btn-sm z-depth-0" role="button" style="font-size:12px;"><i class="icon-BibTeX"></i> BibTeX</a></label>
        <input type="checkbox" name="BibTeX_{{ link.bibtex }}" id="BibTeX_{{ link.bibtex }}" data-toggle="toggle">
      </p>
      <div class="hide" style="display: none">
        <button class="copy_btn" data-clipboard-target="#{{ link.bibtex }}_bib">
          <img class="clippy" src="/assets/images/clippy.svg" alt="Copy to clipboard">
        </button>
        <pre><code id="{{ link.bibtex }}_bib">{{ link.bibtex }}</code></pre>
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

