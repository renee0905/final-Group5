---
title: Gallery index
layout: index
---

<div id = "gallery">
  {% assign sorted_exhibits = site.exhibits | sort: "date" %}
  {% for exhibit in sorted_exhibits %}
    {% assign licence_url = site.data.licences | find: "licence", exhibit.licence %}
    {% assign creator = site.data.creators | find: "name", exhibit.creator %}
    <div class = "grid_cell">
      <a href = "{{ exhibit.url | relative_url }}"><img src="{{ exhibit.image-url }}" class="gallery_thumb"></a>
      <p class = "caption"><a href = "{{ exhibit.url | relative_url }}">{{ exhibit.title }}</a> by <a href = "{{ creator.homepage }}">{{ exhibit.creator }}</a></p>
      <p><a href="{{ licence_url.url }}">{{ exhibit.licence }}</a></p>
    </div>
  {% endfor %}
</div>
