---
layout: default
title: Projects
permalink: /projects/
---
# My Projects

Welcome to my projects page! Here you can see all of my work and research.

{% for post in site.posts %}
  <article>
    <h2><a href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a></h2>
    <p>{{ post.excerpt | strip_html | truncate: 160 }}</p>
  </article>
{% endfor %}
