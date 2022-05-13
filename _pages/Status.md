---
layout: single
title: "Statuspage"
excerpt: "Zi Data Science Lab Statuspage"
permalink: /status/
---

<iframe title="" aria-label="Tabelle" id="datawrapper-chart-7bIKa" src="https://datawrapper.dwcdn.net/7bIKa/5/" scrolling="no" frameborder="0" style="border: none;" width="780" height="380"></iframe>


### Meldungen

{% for post in site.posts %}
{% if post.categories contains 'status' | downcase %}
<li>
<a href="{{post.url}}">{{post.title}}</a><span class="statusbadge">{{post.Status}}</span>
</li>
{% endif %}
{% endfor %}

