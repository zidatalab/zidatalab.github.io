---
layout: single
title: "Statuspage"
excerpt: "Zi Data Science Lab Statuspage"
permalink: /status/
---

### Übersicht

<iframe title="Stand der Impfkampagne nach Bundesländern" aria-label="Tabelle" id="datawrapper-chart-zA0AE" src="https://datawrapper.dwcdn.net/zA0AE/48/" scrolling="no" frameborder="0" style="border: none;" width="800" height="801"></iframe>

*Hinweis: Später wird hier eine Tabelle mit dem Infrastrukturstatus erscheinen.*

### Meldungen

{% for post in site.posts %}
{% if post.categories contains 'status' | downcase %}
<li>
<a href="{{post.url}}">{{post.title}}</a> ({{post.Beginn}})
</li>
{% endif %}
{% endfor %}

