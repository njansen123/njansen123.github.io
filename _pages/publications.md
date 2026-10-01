---
layout: page
permalink: /publications/
title: publications
description:
years: [2026,2025,2024,2023,2022,2021,2020,2019,2018,2017,2016,2015,2014,2013,2012,2011,2010]
nav: true
nav_order: 1
scholar:
  last_name: [Jansen]
  first_name: [Nils]

---
My publication record includes <b>98</b> conference papers, <b>20</b> journal articles, <b>7</b> book chapters, <b>6</b> edited volumes, <b>3</b> Dagstuhl reports, and <b>1</b> editorial (as of October 2026).

Check also the list on my <b><a href='https://ai-fm.org/publications/' target='_blank'>group page</a></b>, <b><a href='https://scholar.google.com/citations?hl=de&user=zUavkyEAAAAJ' target='_blank'>Google Scholar</a></b>, or <b><a href='https://dblp.org/pid/32/8421-1.html' target='_blank'>DBLP</a></b>.


<!-- _pages/publications.md -->
<div class="publications">

{%- for y in page.years %}
  <h2 class="year">{{y}}</h2>
  {% bibliography -f papers -q @*[year={{y}}]* %}
{% endfor %}

</div>
