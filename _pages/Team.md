---
layout: single
author_profile: false
permalink: /team/
title: "Our Team"
header:
  overlay_filter: 0.7 # same as adding an opacity of 0.5 to a black background
  caption: "Photo: [**Pexels**](https://www.pexels.com/photo/abstract-art-blur-bright-373543/)"
  overlay_image: assets/images/pexels-photo-373543.jpeg
classes: wide
---

Our team is small but dedicated. If your're interested in collaborating or joining, please speak to [Lars](https://twitter.com/l_kroll).

<div class="teamwrapper">
    {% for author in site.data.authors %}
    <div>
        {% if author[1].avatar %}
        <div class="author__avatar">
            <img src="{{ author[1].avatar }}" alt="{{ author[1].name }}" itemprop="image">
        </div>
        {% else %}
        <div class="author__avatar">
            <img src="/assets/images/adult-anonymous.jpg" alt="{{ author[1].name }}" itemprop="image">
        </div>
        {% endif %}
        <strong>{{ author[1].name }}</strong><br>
        {% if author[1].bio %}
        <i>{{ author[1].bio | markdownify }}</i>
        {% endif %}
    </div>
    {% endfor %}
</div>
