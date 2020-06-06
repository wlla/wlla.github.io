---
permalink: /index/site-map.html
# just made it a longer permalink so to keep logic uniform below
id: site-map
layout: home-page
title: Site Map
meta: Accessibility, WCAG, Components, Keyboard Accessibility, 404
category: root
status: draft
---

{% for cat in site.data.map %}{% if cat.level == "first" %}
  <h2><a href="https://willaarmstrong.com/{{ cat.id }}">{{ cat.name }}</a></h2>
  <ul>
  {% for item in site.data.map %}{% if item.parent == cat.id %}
    <li><a href="https://willaarmstrong.com/{{ item.parent }}/{{ item.id }}">{{ item.name }}</a></li>
  {% endif %}
  {% endfor %}
  </ul>
{% endif %}
{% endfor %}
