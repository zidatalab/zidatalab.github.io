---
layout: single
title: "News from the Lab"
excerpt: "Infos on our ongoing work. Everything here is work in progress, for official news or statements on or by Zi head over to [zi.de](https://www.zi.de)"
header:
  overlay_filter: 0.7 # same as adding an opacity of 0.5 to a black background
  caption: "Photo: [**Pexels**](https://www.pexels.com/photo/abstract-art-blur-bright-373543/)"
  overlay_image: assets/images/pexels-photo-373543.jpeg
permalink: /news/
---

{% assign categories_max = 0 %}
{% for category in site.categories %}
{% if category[1].size > categories_max %}
{% assign categories_max = category[1].size %}
{% endif %}
{% endfor %}

{% for i in (1..categories_max) reversed %}
{% for category in site.categories %}
{% if category[1].size == i %}
<section id="{{ category[0] | slugify | downcase }}" class="taxonomy__section">
<h2 class="archive__subtitle">{{ category[0] }}</h2>
<div class="entries-{{ page.entries_layout | default: 'list' }}">
{% for post in category.last %}
{% include archive-single.html type=page.entries_layout %}
{% endfor %}
</div>
<a href="#page-title" class="back-to-top">{{ site.data.ui-text[site.locale].back_to_top | default: 'Back to Top' }} &uarr;</a>
</section>
{% endif %}
{% endfor %}
{% endfor %}
