---

layout: page
title: Software solutions
---



{% assign existing_screenshots = site.static_files 
  | where_exp: "file", "file.extname == '.png'" 
  | where_exp: "file", "file.path contains 'img/screenshots/'"
  | map: "basename"
%}

<ul class="content-list" id="tools-list">
  <li>
    <div class="row">
      <div class="col-6">
        <h3>Cognate search</h3>
        <h5>Detecting cognate candidates</h5>
        <p>Language-independent tool for detecting cognates/loan words based on semantic (distributional) and phonological (graphemic) similarity.</p>
        <a href="https://github.com/acoli-repo/cognate-search">More</a>
      </div>
      <div class="col-2">
        <blockquote>
<p>"adventure"@en: similar words from French:</p>
</blockquote>
        <pre><code>aventure   0.88 1.00 0.78
adhérent   0.58 0.61 0.56
accentuer  0.51 0.59 0.44
adversaire 0.40 0.34 0.50
adverse    0.33 0.26 0.44
adjacent   0.32 0.25 0.44
aventurier 0.15 0.09 0.60
adverbe    0.18 0.11 0.44
...</code></pre>
      </div>
    </div>
  </li>
  <li>

{% for tool in site.data.software %}
  {% assign main_screenshot = tool.folder | append: "-main" %}
  
  <li>
    <div class="row">
      <div class="col-6">
        <h3>{{ tool.name }}</h3>
        <h5>{{ tool.full-name }}</h5>
        <p>{{ tool.description | markdownify }}</p>
        <a href="{{ tool.folder }}">More</a>
      </div>
      <div class="col-2">
        {% if existing_screenshots contains main_screenshot %}
        <img src="../img/screenshots/{{ main_screenshot }}.png"/>
        {% endif %}
      </div>
    </div>
  </li>
  <li>
      
  </li>
{% endfor %}
</ul>
