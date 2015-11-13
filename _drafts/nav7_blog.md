---
layout: page
title: Blog
permalink: /blog/
active_nav: Blog
---

probably will be removed - just wanted to keep the original blog functionality somewhere for now

<div class="home">

  <h1 class="page-heading">Posts</h1>

  <ul class="post-list">
    {% for post in site.posts %}
      <li>
        <span class="post-meta">{{ post.date | date: "%b %-d, %Y" }}</span>

        <h2>
          <a class="post-link" href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
        </h2>
      </li>
    {% endfor %}
  </ul>

  <p class="rss-subscribe">subscribe <a href="{{ "/feed.xml" | prepend: site.baseurl }}">via RSS</a></p>

</div>

{% for post in site.posts %}
  {% if post.imageid %}
    {% capture imageurl %}http://res.cloudinary.com/{{site.cloudinary_id}}/image/upload/{{post.thumbnail_options}}/{{post.imageid}}{% endcapture %}
  {% elsif research.imageurl %}
    {% capture imageurl %}{{post.imageurl}}{% endcapture %}
  {% endif %}

  <article class="card card-block" style="clear: both;">
    <h4 style="text-align: {% cycle 'headingcycle': 'right', 'left' %};">
        <a href="{{ research.url | prepend: site.baseurl }}">{{ research.title }}</a>
    </h4>
    <img src="{{ imageurl }}" style="margin: 15px; float: {% cycle 'imagecycle': 'left', 'right' %};" />
    <div>
      
      {{ research.content }}
    </div>

    <div style="clear: both;"></div>
  </article>
{% endfor %}

