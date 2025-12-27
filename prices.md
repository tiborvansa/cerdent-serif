---
title: Ceník
layout: page
description: About
bodyClass: page-about
---

Cenový přehled hlavních výkonů. 



{% assign grouped_prices = site.data.prices | group_by: "category" %}
{% for group in grouped_prices %}
<h2>{{ group.name }}</h2>
<ul style="padding-left:0; list-style:none;">
  {% for item in group.items %}
  <li style="display:flex; justify-content:space-between; align-items:center; padding:2px 0;">
    <span>{{ item.action }}</span>
    <span style="min-width:80px; text-align:right; padding-left:1em;">{{ item.price }} Kč</span>
  </li>
  {% endfor %}
</ul>
{% endfor %}


