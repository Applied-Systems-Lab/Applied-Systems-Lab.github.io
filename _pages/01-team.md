---
layout: page
permalink: /team/
title: team
description: 
---

{% for member in site.members | sort:"startdate" %} {% if member.enddate == null %} <!-- exclude alumni/previous -->

<!-- The paddingtop and margin-top edits allow anchors to link properly. -->
<div id = "{{member.name | replace: ' ', '-'}}" class="row" style="padding-top: 60px; margin-top: -60px;">
        <!-- Added an if statement here to allow for image_url update -->
        {% if member.image %}
          <img style="float: right; width: 25%; padding-left: 20px;" src="{{ member.image | prepend: '/assets/img/' | prepend: site.baseurl | prepend: site.url }}" alt="photo of {{member.name}}">
          <!-- <img style="float: right; width: 42%; padding-left: 20px;" src="{{ member.image | prepend: '/assets/img/' | prepend: site.baseurl | prepend: site.url }}" alt="photo of {{member.name}}"> -->
        {% elsif member.imageurl %}
          <img style="float: right; width: 25%; padding-left: 20px;" src="{{ member.imageurl }}" alt="photo of {{member.name}}">
        {% endif %}
    <div>
        <h4>{{member.name}}{% if member.degrees %}, {{member.degrees}} {% endif %}</h4> 
        {% if member.pronouns %}
          <em>{{member.pronouns}}</em> <br>
        {% endif %}
        {{member.position}} <br>
        <i class="fa fa-envelope"></i> <em>{{member.email}}</em> <br>
        {% if member.website %}
          <i class="fa fa-globe"></i> <a href= "{{member.website}}" target="_blank">{{member.website}}</a> <br>
        {% endif %}
        {% if member.github %}
          <i class="fab fa-github"></i> <a href= "https://github.com/{{member.github}}" target="_blank"> {{member.github}} </a> <br>
        {% endif %}
        {% if member.scholar %}
          <i class="ai ai-google-scholar"></i> <a href= "http://scholar.google.com/citations?user={{member.scholar}}" target="_blank"> Scholar Citations </a> <br>
        {% endif %}
        {% if member.orcid %}
          <i class="ai ai-orcid"></i> <a href="http://{{member.orcid}}" target="_blank"> {{member.orcid}}</a> <br>
        {% endif %}

    </div>
    <div class="col-sm-8">
        <p class="text-justify">{{member.description | markdownify}}</p>
    </div>
</div>
<hr>
{% endif %} {% endfor %}

---

## alumni

{% for alum in site.members | sort: "enddate" | reverse %}
{% if alum.enddate != null %} 

<!-- The paddingtop and margin-top edits allow anchors to link properly. -->
<div id = "{{alum.name | replace: ' ', '-'}}" class="row" style="padding-top: 60px; margin-top: -60px; padding-bottom: 20px;">
  <strong>{{alum.name}}{% if alum.degrees %}, {{alum.degrees}} {% endif %}</strong> <br>
  <!-- <i>previously:</i> {{alum.previously}} <br> -->
  {% if alumn.position %} <i>Current Position:</i> {{alum.position}}<br> {% endif %}
  {% if alum.website %} <i class="fa fa-globe"></i> <a href= "{{alum.website}}" target="_blank">{{alum.website}}</a>  {% endif %}
</div>

{% endif %}
{% endfor %}

---