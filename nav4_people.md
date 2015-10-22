---
layout: page
title: People
permalink: /people/
active_nav: People
---

We have some great people working at the Dean Lab - meet some of them below.

{% raw %}
<div class="container">
  <div class="row">
{% endraw %}

{% for person in site.people %}
  {% if person.imageid %}
    {% capture imageurl %}http://res.cloudinary.com/{{site.cloudinary_id}}/image/upload/{{person.thumbnail_options}}/{{person.imageid}}{% endcapture %}
  {% elsif person.imageurl %}
    {% capture imageurl %}{{person.imageurl}}{% endcapture %}
  {% endif %}

  {% cycle '', '', '', '</div><div class="row">' %}
  <div class="col-sm-4">
    <div class="card">
      <img alt="100%x200" class="card-img-top img-responsive" style="display: block;" src="{{ imageurl }}">
      <div class="card-block">

      <h3 class="card-title"><a href="{{ person.url | prepend: site.baseurl }}">{{ person.name }}</a></h3>
      <h4>{{ person.title }}</h4>
      <p class="card-text">{{ person.description }}</p>
      <p class="card-text"><small class="text-muted"><a href="{{ person.url | prepend: site.baseurl }}">More...</a></small></p>
    </div>
  </div>
</div>
{% endfor %}

{% raw %}
  </div>
</div>
{% endraw %}




