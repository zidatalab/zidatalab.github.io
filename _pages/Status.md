---
layout: single
title: "Statuspage"
excerpt: "Zi Data Science Lab Statuspage"
permalink: /status/
---

### Übersicht

<iframe title="Stand der Impfkampagne nach Bundesländern" aria-label="Tabelle" id="datawrapper-chart-7bIKa" src="https://datawrapper.dwcdn.net/7bIKa/5/" scrolling="no" frameborder="0" style="border: none;" width="800" height="801"></iframe>


### Meldungen

{% for post in site.posts %}
{% if post.categories contains 'status' | downcase %}
<li>
<a href="{{post.url}}">{{post.title}}</a><span class="statusbadge">{{post.Status}}</span>
</li>
{% endif %}
{% endfor %}

