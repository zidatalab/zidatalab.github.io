---
layout: single
author_profile: false
permalink: /team/
title: "Our Team"
---

{% for author in site.data.authors %}
{% if author[1].avatar %}
<div class="author__avatar">
<img src="{{ author.avatar }}" alt="{{ author.name }}" itemprop="image">    
</div>
{% endif %}
**{{ author[1].name }}**
{% if author[1].bio %}
<div class="author__bio" itemprop="description">
{{ author[1].bio | markdownify }}
</div>
{% endif %}    
{% endfor %}
