---
layout: single
author_profile: false
permalink: /team/
title: "Our Team"
---


{% for author in site.data.authors %}
{% increment authorid %}
  <div>Name: {site.data.authors[authorid].name } </div>
{% endfor %}


