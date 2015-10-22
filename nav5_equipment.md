---
layout: page
title: Equipment
permalink: /equipment/
active_nav: Equipment
---

Some of the equipment here at the Dean Lab

{% raw %}
<div class="container">
  <div class="row">
{% endraw %}

{% for equip in site.equipment %}
  {% if equip.imageid %}
    {% capture imageurl %}http://res.cloudinary.com/{{site.cloudinary_id}}/image/upload/{{equip.thumbnail_options}}/{{equip.imageid}}{% endcapture %}
  {% elsif equip.imageurl %}
    {% capture imageurl %}{{equip.imageurl}}{% endcapture %}
  {% endif %}

  {% cycle '', '', '', '', '</div><div class="row">' %}
  <div class="col-sm-3">
    <div class="card">
      <img alt="100%x200" class="card-img-top img-responsive" style="display: block;" src="{{ imageurl }}">
      <div class="card-block">

      <h3 class="card-title"><a href="{{ equip.url | prepend: site.baseurl }}">{{ equip.title }}</a></h3>
      <p class="card-text">{{ equip.content }}</p>
      <p class="card-text"><small class="text-muted"><a href="{{ equip.url | prepend: site.baseurl }}">More...</a></small></p>
    </div>
  </div>
</div>
{% endfor %}

{% raw %}
  </div>
</div>
{% endraw %}

