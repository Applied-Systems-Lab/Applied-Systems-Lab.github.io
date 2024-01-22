---
layout: page
title: networks
category: research
description: 
    This is a description for this page

---

<div class="post">

  <div style="overflow: hidden;">
  <h1 class="post-title">{{ page.title }}</h1>
  <h5 class="post-description">{{ page.description }}</h5>
  
  {% for item in site.posts %}
    {% if item.group == page.title %}
      {{item.group}} ?= {{page.title}}
      <div>
        {{item.title}}
      </div>
      <div>
        {{ item.content }}
      </div>
    {% endif %}
  {% endfor %}

  </div>
</div>