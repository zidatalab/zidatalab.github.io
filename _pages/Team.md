---
layout: single
author_profile: false
permalink: /team/
title: "Our Team"
classes: wide
---

Our team is small but dedicated. If your're interested to collaborate or join, speak to [Lars]({{ site.data.authors[lars].links[Twitter]}}).

<div class="teamwrapper">
{% for author in site.data.authors %}
<div>
{% if author[1].avatar %}
<div class="author__avatar">
<img src="{{ author[1].avatar }}" alt="{{ author[1].name }}" itemprop="image">    
</div>
{% else %}
<div class="author__avatar">
<img src="/assets/images/adult-anonymous-art-business-375902.jpg" alt="{{ author[1].name }}" itemprop="image">
</div>
{% endif %}
<p><strong>{{ author[1].name }}</strong><br>
{% if author[1].bio %}
{{ author[1].bio | markdownify }}
{% endif %}    
</p>
</div>
{% endfor %}
</div>
