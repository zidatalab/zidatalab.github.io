---
layout: single
author_profile: false
permalink: /team/
title: "Our Team"
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
<h5>{{ author[1].name }}<h5>
{% if author[1].bio %}
<p><em>{{ author[1].bio | markdownify }}</em></p>
{% endif %}    
</div>
{% endfor %}
</div>
