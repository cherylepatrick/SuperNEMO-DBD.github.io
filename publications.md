---
layout: page
title: Publications and Media
---

SuperNEMO Papers
----------------
Journal papers from the SuperNEMO experiment

{% assign pubs_by_date = (site.publications | sort:"date") | reverse %}
{% for pub in pubs_by_date %}
<a href="http://dx.doi.org/{{ pub.doi }}" target="_blank"> <strong>{{pub.title }}</strong></a> _{{ pub.journal }}_, {{ pub.date | date_to_long_string }}
<a onClick='$( "#{{pub.doi| replace: ".", "_" | replace: "/","_"}}" ).toggle();
this.text=(($("#{{pub.doi| replace: ".", "_" | replace: "/","_"}}").is(":visible"))?"Less...":"More...");
'>More...</a>
<div style="display:none; overflow:auto" id="{{pub.doi| replace: ".", "_" | replace: "/","_"}}">
{% if pub.image_url %}
<img src="{{pub.image_url}}" style="float:right; height:20em">
{% endif %}
<p>{{pub.abstract}}</p>
</div>
{% endfor %}

NEMO-3 Papers
-------------
Papers from SuperNEMO's predescessor, NEMO-3

{% assign n3pubs_by_date = (site.nemothreepubs  | sort:"date") | reverse %}
{% for pub in n3pubs_by_date %}
<a href="http://dx.doi.org/{{ pub.doi }}" target="_blank"> <strong>{{pub.title }}</strong></a> _{{ pub.journal }}_, {{ pub.date | date_to_long_string }}
<a onClick='$( "#{{pub.doi| replace: ".", "_" | replace: "/","_"}}" ).toggle();
this.text=(($("#{{pub.doi| replace: ".", "_" | replace: "/","_"}}").is(":visible"))?"Less...":"More...");
'>More...</a>
<div style="display:none" id="{{pub.doi| replace: ".", "_" | replace: "/","_"}}">
<img src="{{pub.image_url}}" width="50%" ALIGN="right">
<p>{{pub.abstract}}</p>
</div>
{% endfor %}

