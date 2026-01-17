---
title: Ceník - Zubní ordinace Cerdent
layout: page
description: Cenový přehled stomatologických služeb v ordinaci Cerdent. Transparentní ceny za dentální hygienu, ošetření kazů, protetiku a další služby.
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


{% if site.data.insurances %}
<div class="strip strip">
  <div class="container pt-2 pb-2 pt-md-4 pb-md-4">
    <h1 class="text-center">Máme smlouvy s pojišťovnami</h1>
    <div class="row justify-content-center align-items-center">
      {% for insurance in site.data.insurances %}
      <div class="col-6 col-md-2 mb-2">
        <div class="insurance-logo">
          {% if insurance.image %}
          <div class="insurance-image">
            <img alt="{{ insurance.title }} logo" 
                 src="{{ insurance.image.url | relative_url }}" 
                 class="img-fluid insurance-logo-img" />
          </div>
          {% endif %}
        </div>
      </div>
      {% endfor %}
    </div>
  </div>
</div>
{% endif %}