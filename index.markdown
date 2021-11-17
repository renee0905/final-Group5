---
title: Gallery index
layout: index
---

<div class="gallery">
  {% for exhibit in site.exhibits %}
    {% assign licence_url = site.data.licences | find: "licence", exhibit.licence %}
    {% assign creator = site.data.creators | find: "name", exhibit.creator %}
    <figure>
      <a href = "{{ exhibit.url | relative_url }}"><img src="{{ exhibit.image-url }}" class="gallery_thumb"></a>
      <p><a href = "{{ exhibit.url | relative_url }}">{{ exhibit.title }}</a> by <a href = "{{ creator.homepage }}">{{ exhibit.creator }}</a></p>
      <p><a href="{{ licence_url.url }}">{{ exhibit.licence }}</a></p>
    </figure>
  {% endfor %}
</div>
