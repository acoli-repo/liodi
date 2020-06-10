---

layout: page
title: Datasets
---

<ul class="content-list" id="tools-list">
{% for dataset in site.data.datasets %}
  <li>
    <div class="row">
      <div class="col-6">
        <h3>{{ dataset.name }}</h3>
        <h5>{{ dataset.full-name }}</h5>
        <p>{{ dataset.description | markdownify }}</p>
        <a href="{{ dataset.link }}">Download</a>
      </div>
    </div>
  </li>
  <li>
      
  </li>
{% endfor %}
</ul>
