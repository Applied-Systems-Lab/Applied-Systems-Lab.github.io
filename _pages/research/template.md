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
  
  {% for post in site.posts | where: "group", page.title %}
  <div>
    {{post.title}}
  </div>
  <div>
    {{ post.content }}
  </div>
  {% endfor %}

  </div>
</div>