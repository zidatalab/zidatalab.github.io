---
layout: single
author_profile: false
permalink: /team/
title: "Our Team"
---


{% for author in site.data.authors %}
  <p>Name: {site.data.authors[increment authorid].name } </p>
{% endfor %}


