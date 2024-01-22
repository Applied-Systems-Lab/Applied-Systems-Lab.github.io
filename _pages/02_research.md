---
layout: page
permalink: /research/
title: research
description: 
---


TODO: make pretty clickable things


{% assign topics = site.pages | sort: "title" | where: "category", page.title %}

{% for topic in topics %}

## <a class="page-link" href="{{ topic.url | prepend: site.baseurl | prepend: site.url }}">{{ topic.title }}</a>
{{topic.description}}

{% endfor %}