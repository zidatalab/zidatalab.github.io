---
layout: single
author_profile: false
permalink: /team/
title: "Our Team"
---

{% for author in site.data.authors %}
{% if author[1].avatar %}
<div class="author__avatar">
<img src="{{ author[1].avatar }}" alt="{{ author[1].name }}" itemprop="image">    
</div>
{% endif %}
**{{ author[1].name }}**
{% if author[1].bio %}
{{ author[1].bio | markdownify }}
{% endif %}    

{% endfor %}
