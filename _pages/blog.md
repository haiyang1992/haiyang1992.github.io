---
layout: archive
title: Blog
permalink: /blog/
---

#### [Browse by Categories](https://haiyang1992.github.io/categories/){: .btn .btn--info} [Browse by Tags](https://haiyang1992.github.io/tags/){: .btn .btn--info}

{% include base_path %}
{% capture written_year %}'None'{% endcapture %}
{% for post in site.posts %}
  {% capture year %}{{ post.date | date: '%Y' }}{% endcapture %}
  {% if year != written_year %}
   <h2 id="{{ year | slugify }}" class="archive__subtitle">{{ year }}</h2>
   {% capture written_year %}{{ year }}{% endcapture %}
  {% endif %}
  {% include archive-single.html %}
{% endfor %}