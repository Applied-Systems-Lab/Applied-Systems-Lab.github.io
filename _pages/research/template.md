---
layout: page
title: template
category: research
description: 
    This is a description for this page

---

<div class="post">

  <div style="overflow: hidden;">
  <h1 class="post-title">{{ page.title }}</h1>
  <h5 class="post-description">{{ page.description }}</h5>
  
  {% for post in site.posts %}
    {% if post.group == page.title %}
      {{post.group}} ?= {{page.title}}
      <div>
        {{post.title}}
      </div>
      <div>
        {{ post.content }}
      </div>
    {% endif %}
  {% endfor %}

  </div>
</div>