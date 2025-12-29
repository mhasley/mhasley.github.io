---
layout: default
title: Projects
permalink: /projects/
pagination:
  enabled: true
  per_page: 4
  collection: posts
---
<div class="container">
  <h1>{{ page.title }}</h1>

  <div class="row">
    {% for post in paginator.posts %}
      {% if forloop.index <= 1 %}
      <div class="col col-12">
        <article class="article-first">
          <div class="article-image-first" style="background-image: url({{ "/img/" | prepend: site.baseurl | append: post.image }})">
            <div class="article-content-first">
              <h2 class="article-title"><a href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a></h2>
              <p class="article-excerpt">{% if post.description %}{{ post.description | strip_html | truncate: 163 }}{% else %}{{ post.content | strip_html | truncate: 163 }}{% endif %}</p>
              <a href="{{ post.url | prepend: site.baseurl }}" class="button read-more">Read More</a>
            </div>
          </div>
        </article>
      </div>
      {% else %}
      <article class="article col col-12 col-t-6">
        <div class="article-box">
          <a href="{{ post.url | prepend: site.baseurl }}" class="article-image" style="background-image: url({{ "/img/" | prepend: site.baseurl | append: post.image }})"></a>
          <div class="article-content">
            <h2 class="article-title"><a href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a></h2>
            <p class="article-excerpt">{% if post.description %}{{ post.description | strip_html | truncate: 135 }}{% else %}{{ post.content | strip_html | truncate: 135 }}{% endif %}</p>
          </div>
        </div>
      </article>
      {% endif %}
    {% endfor %}
  </div>

  <div class="row">
    <div class="col col-12">
      {% include pagination.html %}
    </div>
  </div>
</div>
