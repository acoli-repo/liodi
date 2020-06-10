---

layout: page
title: Standards
---

<ul class="content-list" id="tools-list">
{% for std in site.data.standards %}
  <li>
    <div class="row">
      <div class="col-6">
        <h3>{{ std.name }}</h3>
        <h5>{{ std.full-name }}</h5>
        <p>{{ std.description | markdownify }}</p>
        <a href="{{ std.folder }}">More</a>
      </div>
    </div>
  </li>
  <li>
      
  </li>
{% endfor %}
</ul>
