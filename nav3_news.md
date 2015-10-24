---
layout: page
title: News
permalink: /news/
active_nav: News
categories: jekyll update
---

{% for newsitem in site.news %}
  {% capture thecycle %}{% cycle 'left', 'right' %}{% endcapture %}

  {% if newsitem.imageid %}
    {% capture imageurl %}http://res.cloudinary.com/{{site.cloudinary_id}}/image/upload/{{newsitem.thumbnail_options}}/{{newsitem.imageid}}{% endcapture %}
  {% elsif newsitem.imageurl %}
    {% capture imageurl %}{{newsitem.imageurl}}{% endcapture %}
  {% endif %}

  <div class="media card card-block">

    {% if thecycle == 'left' and imageurl %}
    <a class="media-left" href="{{ newsitem.url | prepend: site.baseurl }}">
      <img alt="100%x200" class="media-object" src="{{ imageurl }}">
    </a>
    {% endif %}

    <div class="media-body">
      <h4 class="media-heading"><a href="{{ newsitem.url | prepend: site.baseurl }}">{{ newsitem.title }}</a></h4>
        {{ newsitem.content }}
    </div>


    {% if thecycle == 'right' and imageurl %}
    <a class="media-right" href="{{ newsitem.url | prepend: site.baseurl }}">
      <img alt="100%x200" class="media-object" src="{{ imageurl }}">
    </a>
    {% endif %}
   

  </div>
    
{% endfor %}
