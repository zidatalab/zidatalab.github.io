---
author: Lars
title: Our Public COVID-19 Dashboard is online
excerpt: ""
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

We created a dashboard in early May to inform the public about the Zi's assessment of the federal government's relaxation decisions. 

The dashboard is based on a (paper)[https://www.zi.de/fileadmin/images/content/PMs/Fruehindikator_fuer_ein_Management_des_Pandemiegeschehens.pdf] published at the same time in which we draw attention to alternatives to the fixed limit of new infections per inhabitant that has been decided. Our central point is that a fixed population-based limit does not take sufficient account of regional capacities for patient care.

We created the dashboard using *Gnu R* with heavy usage of `tidyverse`, `flexdashboard` and `plotly`. For the estimation of the Reproduction Number R of COVID-19 cases we used the package `EpiEstim`.

**Links:**
The Code is published (here)[https://github.com/zidatalab/covid19dashboard].
If you are interested in the dashboard (see it here)[https://www.zidatasciencelab.de/covid19dashboard/Start].
