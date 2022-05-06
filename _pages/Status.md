---
layout: single
title: "Statuspage"
excerpt: "Zi Data Science Lab Statuspage"
permalink: /status/
---

### Übersicht

Test:

<iframe title="Stand der Impfkampagne nach Bundesländern" aria-label="Tabelle" id="datawrapper-chart-zA0AE" src="https://datawrapper.dwcdn.net/zA0AE/48/" scrolling="no" frameborder="0" style="border: none;" width="800" height="801"></iframe>


### Meldungen

{% for item in site.categories[status] %}
  <a href="{{ item.url }}" target="_self" draggable="false">
    {{ item.title }}
  </a>
{% endfor %}

