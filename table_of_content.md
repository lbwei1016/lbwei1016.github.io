---
layout: page
title: Table of Contents
usemathjax: true
---
{% for collection in site.collections %}
  {% if collection.label != "posts" %}
  <h2>{{ collection.label }}</h2>
  <ul>
  {% for item in site[collection.label] %}
  <li><a href="{{ item.url }}">{{ item.title }}</a></li>
  {% endfor %}
  </ul>
  {% endif %}
{% endfor %}

$$\lambda$$
$$x = {-b \pm \sqrt{b^2-4ac} \over 2a}.$$
