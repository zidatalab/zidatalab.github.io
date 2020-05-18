---
layout: single
author_profile: false
permalink: /team/
title: "Our Team"
---

These are the people running our lab:

{% for author in site.data.authors %}
{% assign theauthor = increment authorid %}
<p>Name: {theauthor} </p>
{% endfor %}


