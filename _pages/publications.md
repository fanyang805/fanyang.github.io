---
layout: page
permalink: /publications/
title: Publications
description:
years: [2021, 2020, 2018, 2017]
posteryear: [2019, 2018, 2017]
nav: true
---

<!-- ## Publications -->

<div class="publications">

{% assign y= 2020 %}
  {% bibliography -f thesis -q @*[year={{y}}]* %}

</div>

<div class="publications">

{% for y in page.years %}
  <h2 class="year">{{y}}</h2>
  {% bibliography -f papers -q @*[year={{y}}]* %}
{% endfor %}

</div>

<br/><br/>
## Workshop publications

<div class="publications">

{% for y in page.posteryear %}
  <h2 class="year">{{y}}</h2>
  {% bibliography -f abs -q @*[year={{y}}]* %}
{% endfor %}

</div>
