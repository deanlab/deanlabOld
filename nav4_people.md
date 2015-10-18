---
layout: page
title: People
permalink: /people/
---

This is the People page, which will contain the index for the People custom collection

{% for person in site.people %}
  {% capture thecycle %}{% cycle 'odd', 'even' %}{% endcapture %}

  {% if person.imageid %}
    {% capture imageurl %}http://res.cloudinary.com/{{site.cloudinary_id}}/image/upload/{{person.thumbnail_options}}/{{person.imageid}}{% endcapture %}
  {% elsif person.imageurl %}
    {% capture imageurl %}{{person.imageurl}}{% endcapture %}
  {% endif %}
  


  <div class="media card card-block">
    {% if thecycle == 'odd' and imageurl %}
      <a class="media-left" href="#">
        <img src="{{ imageurl }}" class="img-responsive" >
      </a>
    {% endif %}

    <div class="media-body">
      <h4 class="media-heading">
        <a href="{{ person.url | prepend: site.baseurl }}">{{ person.name }}</a>
      </h4>

      <dl>
        <dt>Name</dt>
        <dd>{{ person.name }}</dd>

        {% if person.title %}
        <dt>Title</dt>
        <dd>{{ person.title }}</dd>
        {% endif %}

        {% if person.lab %}
        <dt>Lab</dt>
        <dd>{{ person.lab }}</dd>
        {% endif %}

        {% if person.office %}
        <dt>Office</dt>
        <dd>{{ person.office }}</dd>
        {% endif %}

        {% if person.phone %}
        <dt>Phone</dt>
        <dd>{{ person.phone }}</dd>
        {% endif %}

        {% if person.email %}
        <dt>EMail</dt>
        <dd>{{ person.email }}</dd>
        {% endif %}

        {% if person.twitter %}
        <dt>Twitter</dt>
        <dd>{{ person.twitter }}</dd>
        {% endif %}

        {% if person.facebook %}
        <dt>Facebook</dt>
        <dd>{{ person.facebook }}</dd>
        {% endif %}
      </dl>

      {{ person.content }}
    </div>

    {% if thecycle == 'even' and imageurl %}
      <a class="media-right" href="#">
        <img src="{{ imageurl }}" class="img-responsive" >
      </a>
    {% endif %}
  </div>
{% endfor %}

