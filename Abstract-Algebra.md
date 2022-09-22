---
layout: table
title: Abstract-Algebra
---

<ul>
    {% for item in site[page.title] %}
        <li><a href="{{ item.url }}">{{ item.title }}</a></li>
    {% endfor %}
</ul>