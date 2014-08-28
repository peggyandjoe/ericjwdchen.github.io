---
layout: page
title: Archive
weight: 1
---

<section id="archive">
      {% capture year %}{{ post.date | date: '%Y' }}{% endcapture %}
      {% capture nyear %}{{ post.next.date | date: '%Y' }}{% endcapture %}
      {% if year != nyear %}
        </ul>
        <h3>{{ post.date | date: '%Y' }}</h3>
        <ul class="past">
      {% endif %}
    {% endunless %}
      <li><time>{{ post.date | date:"%d %b" }}</time><a href="{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
  </ul>
</section>
