---
layout: single
author_profile: false
permalink: /team/
title: "Our Team"
---


{% for author in site.data.authors %}
  {{  assign the_author = author }}
  <div>Name: {% the_author.name %} </div>
{% endfor %}


