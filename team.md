---

layout: page
title: LiODi Team
---

{% assign existing_photos = site.static_files 
  | where_exp: "file", "file.extname == '.jpg'"
  | where_exp: "file", "file.path contains 'img/people/'"
  | map: "basename" 
%}

<ul class="content-list" id="team-members">
{% for member in site.data.team %}
  {% assign lastname = member.name 
    | split: " " 
    | last 
    | downcase 
  %}

  <li>
    <div class="team-member row">
      <div class="col-6">
        <h3>{{ member.name }}</h3>
        <ul>
          <li><strong>{{ member.role }}</strong></li>
          <li>{{ member.address }}</li>
          <li><a href="mailto:{{ member.email }}">{{ member.email }}</a></li>
          <li>{{ member.phone | newline_to_br }}</li>
          <li>{{ member.misc }}</li>
        </ul>
      </div>
      <div class="col-2">
        {% if existing_photos contains lastname %}
        <img src="img/people/{{ lastname }}.jpg"/>
        {% endif %}
      </div>
    </div>
  </li>
{% endfor %}
</ul>