---
layout: page
permalink: /publications/
title: publications
description:
years: [2023,2022,2021,2020,2019,2018,2017,2016,2015,2014,2013,2012,2011,2010]
nav: true
nav_order: 1
scholar:
  last_name: [Jansen]
  first_name: [Nils]

---
My peer-reviewed publications. See also my <b><a href='https://scholar.google.com/citations?hl=de&user=zUavkyEAAAAJ' target='_blank'>Google scholar</a></b> or my <b><a href='https://dblp.org/pid/32/8421-1.html' target='_blank'>dblp</a></b> page.

<!-- _pages/publications.md -->
<div class="publications">

{%- for y in page.years %}
  <h2 class="year">{{y}}</h2>
  {% bibliography -f papers -q @*[year={{y}}]* %}
{% endfor %}

</div>
