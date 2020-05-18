---
layout: single
author_profile: false
permalink: /team/
title: "Our Team"
---

These are the people running our lab:

{% for author in site.data.authors %}
    Name: {{ author[1].name }}  
    Rolle: {{ author[1].bio }}
{% endfor %}
