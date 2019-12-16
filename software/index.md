---

layout: page
title: Tools
---

{% assign existing_screenshots = site.static_files 
  | where_exp: "file", "file.extname == '.png' and file.path contains 'img/screenshots/'"
  | map: "basename"
%}

<ul class="content-list" id="tools-list">
{% for tool in site.data.software %}
  {% assign main_screenshot = tool.id | append: "-main" %}
  
  <li>
    <div class="row">
      <div class="col-6">
        <h3>{{ tool.name }}</h3>
        <h5>{{ tool.full-name }}</h5>
        <p>{{ tool.description | markdownify }}</p>
        <a href="{{ tool.id }}">More</a>
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
