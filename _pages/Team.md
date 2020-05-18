---
layout: single
author_profile: false
permalink: /team/
title: "Our Team"
---

These are the people running our lab:

{% for author in site.data.authors %}
    **{ author[1].name }**
    {% if author.bio %}
    <div class="author__bio" itemprop="description">
        {{ author[1].bio | markdownify }}
    </div>
    {% endif %}    
{% endfor %}
