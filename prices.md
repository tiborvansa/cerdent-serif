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
<ul>
  {% for item in group.items %}
  <li>{{ item.action }}: {{ item.price }} Kč</li>
  {% endfor %}
</ul>
{% endfor %}


