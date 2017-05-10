---
layout: page
title: Publications and Media
---

SuperNEMO Papers
----------------
Journal papers from the SuperNEMO experiment

{% assign pubs_by_date = (site.publications | sort:"date") | reverse %}
{% for pub in pubs_by_date %}
<a href="http://dx.doi.org/{{ pub.doi }}" target="_blank"> <strong>{{ pub.title }}</strong></a><br/> _{{ pub.journal }}_ {% if pub.arxiv %}<a href="https://arxiv.org/abs/{{pub.arxiv}}" target="_blank">(arXiv {{pub.arxiv}})</a>{% endif %}, {{ pub.date | date_to_long_string }}
<a role="button" data-toggle="collapse" href="#{{pub.doi| slugify}}" aria-expanded="false" aria-controls="{{pub.doi| slugify}}">Abstract</a>
<div  class="collapse" id="{{pub.doi| slugify}}">
<div class="well" style="overflow:auto">
{% if pub.image_url %}
<img src="{{pub.image_url}}" style="float:right; height:20em">
{% endif %}
<p>{{pub.abstract}}</p>
</div>
</div>
{% endfor %}

NEMO-3 Papers
-------------
Papers from SuperNEMO's predescessor, NEMO-3

{% assign n3pubs_by_date = (site.nemothreepubs  | sort:"date") | reverse %}
{% for pub in n3pubs_by_date %}
<a href="http://dx.doi.org/{{ pub.doi }}" target="_blank"> <strong>{{ pub.title }}</strong></a><br/> _{{ pub.journal }}_ {% if pub.arxiv %}<a href="https://arxiv.org/abs/{{pub.arxiv}}" target="_blank">(arXiv {{pub.arxiv}})</a>{% endif %}, {{ pub.date | date_to_long_string }}
<a role="button" data-toggle="collapse" href="#{{pub.doi| slugify}}" aria-expanded="false" aria-controls="{{pub.doi| slugify}}">Abstract</a>
<div  class="collapse" id="{{pub.doi| slugify}}">
<div class="well" style="overflow:auto">
{% if pub.image_url %}
<img src="{{pub.image_url}}" style="float:right; height:20em">
{% endif %}
<p>{{pub.abstract}}</p>
</div>
</div>
{% endfor %}

