---
layout: experiment
title: Publications and Media
---

<div class="container-fluid" id="top">
  <div class="row">
    <div class="col-xs-9">
<div id="talks" style="display:none">
<h2>Conference talks</h2>

<p>NEMO collaborators present at conferences around the world. Catch up on our progress with this archive of slides.</p>
{% assign sorted_talks = (site.data.talks | sort:"Date") | reverse %}

{% for talk in sorted_talks %}
<p><a href="{{ talk.Pdf }}" target="_blank"> <strong>{{ talk.Title }}</strong></a><br/> presented by {% if talk.Email %}<a href="mailto:{{talk.Email}}?Subject=SuperNEMO%20presentation%20enquiry" target="_top">{% endif %} {{ talk.Author | replace: "'e", "é" }}{% if talk.Email %}</a>{% endif %} {% if talk.Conference %} at <a href="{{talk.ConferenceUrl}}" target="_blank">{{talk.Conference}}</a>{% if talk.City %}, {{talk.City}}{% endif %}{% endif %}, {{ talk.Date | date_to_long_string }}</p>
{% endfor %}
<a href="#beginning">Back to top</a>
</div>

<div id="posters" style="display:none">
<h2>Posters</h2>

<p>SuperNEMO and NEMO-3 posters presented at conferences and schools.</p>
{% assign sorted_posters = (site.data.posters | sort:"Date") | reverse %}

{% for poster in sorted_posters %}
<p><a href="{{ poster.Pdf }}" target="_blank"> <strong>{{ poster.Title }}</strong></a><br/> presented by {% if poster.Email1 %}<a href="mailto:{{poster.Email1}}?Subject=SuperNEMO%20poster%20enquiry" target="_top">{% endif %} {{ poster.Author }}{% if poster.Email1 %}</a>{% endif %} {% if poster.Conference %} at <a href="{{poster.ConferenceUrl}}" target="_blank">{{poster.Conference}}</a>{% endif %}, {{ poster.Date | date_to_long_string }}</p>
{% endfor %}
<a href="#beginning">Back to top</a>
</div>

<div id="articles" style="display:none">
  <h2>NEMO in the News</h2>
  <p>Find out what the world has to say about SuperNEMO and NEMO-3.</p>
  {% assign articles_by_date = (site.public_articles | sort:"date") | reverse %}
  <div class="container-fluid">
    {% for article in articles_by_date %}
    <div class="row">
      <div class='col-xs-2'>
        <a href="{{ article.remoteurl }}" target="_blank"> <img src="{{ article.thumbnail}}" class="img-thumbnail" ></a>
          </div>
      <div class='col-xs-10'>
        <p><a href="{{ article.remoteurl }}" target="_blank"> <strong>{{ article.title }}</strong></a>, from {{ article.media }}, {{ article.date | date_to_long_string }}<br/>
        <i>{{article.abstract}}</i>
        </p>
      </div>
    </div>
    {% endfor %}    <a href="#beginning">Back to top</a>
  </div>
</div>

<div id="papers" style="display:none">
<h2>SuperNEMO Papers</h2>
<p>Journal papers from the SuperNEMO experiment.</p>
{% assign pubs_by_date = (site.publications | sort:"date") | reverse %}
{% for pub in pubs_by_date %}
<p><a href="http://dx.doi.org/{{ pub.doi }}" target="_blank"> <strong>{{ pub.title }}</strong></a><br/> <i>{{ pub.journal }}</i> {% if pub.arxiv %}<a href="https://arxiv.org/abs/{{pub.arxiv}}" target="_blank">(arXiv {{pub.arxiv}})</a>{% endif %}, {{ pub.date | date_to_long_string }}
<a role="button" data-toggle="collapse" href="#{{pub.doi| slugify}}" aria-expanded="false" aria-controls="{{pub.doi| slugify}}">Abstract</a></p>
<div  class="collapse" id="{{pub.doi| slugify}}">
<div class="well" style="overflow:auto">
{% if pub.image_url %}
<img src="{{pub.image_url}}" style="float:right; height:20em" alt="Image from {{pub.title}}">
{% endif %}
<p>{{pub.abstract}}</p>
</div>
</div>
{% endfor %}
<a href="#beginning">Back to top</a>
</div>

<div id="nemo3" style="display:none">
<h2>NEMO-3 Papers</h2>

<p>Papers from SuperNEMO's predescessor, NEMO-3.</p>

{% assign n3pubs_by_date = (site.nemothreepubs  | sort:"date") | reverse %}
{% for pub in n3pubs_by_date %}
<p><a href="http://dx.doi.org/{{ pub.doi }}" target="_blank"> <strong>{{ pub.title }}</strong></a><br/> <i>{{ pub.journal }}</i> {% if pub.arxiv %}<a href="https://arxiv.org/abs/{{pub.arxiv}}" target="_blank">(arXiv {{pub.arxiv}})</a>{% endif %}, {{ pub.date | date_to_long_string }}
<a role="button" data-toggle="collapse" href="#{{pub.doi| slugify}}" aria-expanded="false" aria-controls="{{pub.doi| slugify}}">Abstract</a></p>
<div  class="collapse" id="{{pub.doi| slugify}}">
<div class="well" style="overflow:auto">
{% if pub.image_url %}
<img src="{{pub.image_url}}" style="float:right; height:20em" alt="Image from {{pub.title}}">
{% endif %}
<p>{{pub.abstract}}</p>
</div>
</div>
{% endfor %}
<a href="#beginning">Back to top</a>
</div>

    </div>

    <div class="col-xs-3">
        <div class="square" style="background-color:var(--first-color);" id="talks_btn">
          <div class="content">
            <div class="table">
              <div class="table-cell" >
                Talks
              </div>
            </div>
          </div>
        </div>
        <div class="square" style="background-color:var(--second-color);" id="poster_btn">
          <div class="content">
            <div class="table">
              <div class="table-cell">
                Posters
              </div>
            </div>
          </div>
        </div>
        <div class="square" style="background-color:var(--third-color);" id="article_btn">
          <div class="content">
            <div class="table">
              <div class="table-cell">
                NEMO in the news
              </div>
            </div>
          </div>
        </div>
        <div class="square" style="background-color:var(--fourth-color);" id="paper_btn">
          <div class="content">
            <div class="table">
              <div class="table-cell">
                SuperNEMO papers
              </div>
            </div>
          </div>
        </div>
        <div class="square" style="background-color:var(--fifth-color);" id="nemo3_btn">
          <div class="content">
            <div class="table">
              <div class="table-cell">
                NEMO-3 papers
              </div>
            </div>
          </div>
        </div>
        <div class="square" style="background-color:var(--sixth-color);" id="all_btn">
          <div class="content">
            <div class="table">
              <div class="table-cell">
                Everything
              </div>
            </div>
          </div>
        </div>
    </div>

  </div>
</div>
