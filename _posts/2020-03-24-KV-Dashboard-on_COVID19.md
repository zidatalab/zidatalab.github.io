---
author: Lars
title: Our internal KV COVID-19 Dashboard is online
header:
    overlay_image: assets/posts/2020-05-22-Zi_COVID19_Projektionen.png
    overlay_opacity: 0.3
excerpt: "We created a dashboard in early March to inform the KV Executives about the Zi's projections for future COVID19 developments."
categories: [news] # Pleaser choose from [news,presentations,articles,projects,reports]
tags:
  - covid19
layout: single
author_profile: true
read_time: false
comments: false
share: false
related: false

---

The dashboard is based on a [Methods] desribed in public first here in this [post](https://www.zidatasciencelab.de/reports/Methodenbeschreibung_Projektion_COVID-19/)


We created the dashboard using ***R Shiny*** with heavy usage of `tidyverse`, `gglot` and `shinydashboard`. For the estimation of the Reproduction Number R of COVID-19 cases we used the package `EpiEstim`.

The Dashboard is used since then by severals KVen to prepare for upcoming trends.
