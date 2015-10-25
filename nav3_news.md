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

  <article class="card card-block" style="clear: both;">
    <h4 style="text-align: {% cycle 'headingcycle': 'right', 'left' %};">
        <a href="{{ newsitem.url | prepend: site.baseurl }}">{{ newsitem.title }}</a>
    </h4>
    <img src="{{ imageurl }}" style="margin: 15px; float: {% cycle 'imagecycle': 'left', 'right' %};" />
    <div>
      
      {{ newsitem.content }}
    </div>

    <div style="clear: both;"></div>
  </article>
    
{% endfor %}
