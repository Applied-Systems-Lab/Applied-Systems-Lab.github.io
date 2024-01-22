---
layout: page
title: networks
category: research
description: 
    This is a description for this page
    (specifically the template page)

---

<div class="post"
  
  {% for item in site.posts | where_exp: "item", "item.group == page.title" %}
      <div>
        {{item.title}}
      </div>
      <!-- <div>
        {{ item.content }}
      </div> -->
  {% endfor %}

  </div>
</div>