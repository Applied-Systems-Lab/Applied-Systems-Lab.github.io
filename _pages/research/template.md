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
  
  <!-- {% include category_index.html %} -->

  {% assign items = site.posts | where: "group", "networks" %}

  {% for item in items %}
  <div>
    {{item.title}}
  </div>
  <div>
    {{ item.content }}
  </div>
  {% endfor %}

  </div>
</div>