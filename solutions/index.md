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
<p>"adventure"@en</p>
</blockquote>
<pre><code>"adventure"@en  aventure   0.875000 1.000000 0.777778
                adhérent   0.579403 0.605390 0.555556
                accentuer  0.505341 0.585576 0.444444
                adversaire 0.404759 0.339995 0.500000
                adverse    0.326851 0.258465 0.444444
                adjacent   0.316972 0.246323 0.444444
                aventurier 0.154761 0.088838 0.600000
                adverbe    0.178534 0.111703 0.444444
                ...
</code></pre>
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
