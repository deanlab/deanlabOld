---
layout: page
title: Research
permalink: /research/
active_nav: Research
---

Our research focuses on both fundamental studies, and technological applications of solid state devices at the meso- and nano-scale. General areas of study include electron transport in degenerate many body systems where strong interactions lead to new states of matter and novel electronic behaviour resulting from new device archictectures. Systems that we study include layered materials such as graphene and related heterostructures, transition metal dichalcogenides, and topological insulators as well as more conventional 2D electron systems such as III-V semiconductors. We probe these systems by combining transport studies with a variety of experimental knobs such as applied magnetic and electrostatic fields, variable tempeartures from ambient down to miliKelvin, high vacuum, spatial confinement down to the nano-scale, variable charge carrier densities, and unconventional NMR techniques.

Below please find examples of some broad research topics being studied in our lab; under the equipment tab you can learn more about our experimental capabilities.

{% for research in site.research %}
  {% if research.imageid %}
    {% capture imageurl %}http://res.cloudinary.com/{{site.cloudinary_id}}/image/upload/{{research.thumbnail_options}}/{{research.imageid}}{% endcapture %}
  {% elsif research.imageurl %}
    {% capture imageurl %}{{research.imageurl}}{% endcapture %}
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
