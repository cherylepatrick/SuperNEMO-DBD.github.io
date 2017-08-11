---
layout: page
title: The Collaboration
---

SuperNEMO is an international collaboration comprising physicists and engineers from across Europe and beyond.

<ul>
  {% assign site.data.people.upcasename = (site.data.people.LastName | upcase) %}
  {% assign sorted_people = (site.data.people | sort: 'LastName') %}
  {% for person in sorted_people %}
  <li>
    {% assign emailarray = {{person.Email | split:"@"}} %}
    <a data-toggle="modal" href="#{{ person.FirstName }}{{ person.LastName }}_Modal">{{ person.FirstName }} {{ person.LastName}}</a>
    {% for item in emailarray limit:1 offset:1 %}
    {% assign domain=(item | downcase) %}
    {% endfor %}
{% if site.data.institutions[domain].name %}
{% else %}
{% assign domainarray= {{domain| split:"."}} %}
{% for domainpart in domainarray %}
{% case forloop.index %}
{% when 1 %}
{% when 2 %}
{% assign newdomain = domainpart %}
{% else %}
{% assign newdomain = newdomain | append: "." | append: domainpart %}
{% endcase %}
{% endfor %}
{% capture name_size %}{{ site.data.institutions[newdomain].name |size }}{% endcapture %}
{% if name_size == "0" %}
{% assign domain = "Other" %}
{% else %}
{% assign domain = newdomain %}
{% endif %}
{% endif %}
    {%if site.data.institutions[person.Institution].name %} - {{site.data.institutions[person.Institution].name}}{% endif %}
  </li>
  {% endfor %}
</ul>

{% for person in site.data.people %}
{% assign emailarray = {{person.Email | split:"@"}} %}
{% for item in emailarray limit:1 offset:1 %}
  {% assign domain=(item | downcase) %}
{% endfor %}
{% if site.data.institutions[domain].name %}
{% else %}
  {% assign domainarray= {{domain| split:"."}} %}
  {% for domainpart in domainarray %}
    {% case forloop.index %}
      {% when 1 %}
      {% when 2 %}
      {% assign newdomain = domainpart %}
      {% else %}
        {% assign newdomain = newdomain | append: "." | append: domainpart %}
    {% endcase %}
  {% endfor %}
  {% capture name_size %}{{ site.data.institutions[newdomain].name |size }}{% endcapture %}
  {% if name_size == "0" %}
    {% assign domain = "Other" %}
  {% else %}
{% assign domain = newdomain %}
  {% endif %}
{% endif %}

<div id="{{ person.FirstName }}{{ person.LastName }}_Modal" class="modal fade" role="dialog">
  <div class="modal-dialog">
    <!-- Modal content-->
    <div class="modal-content">
      <div class="modal-header">
        <button type="button" class="close" data-dismiss="modal">&times;</button>
        <h4 class="modal-title">
          {% if person.Photo %}
            <img src="{{person.Photo}}" alt="Picture of {{person.Name}}" class="img-circle" style="height:5em">
              {% elsif site.data.institutions[person.Institution].logo %}
                <img src="{{site.data.institutions[person.Institution].logo }}"
                alt="{{site.data.institutions[person.Institution].name }} logo"
                style="height:3em">
              {% else %}
                <img src="assets/supernemo_logo_v1.0.png" alt="SuperNEMO logo" style="height:3em">
          {% endif %}
          
          {{person.FirstName}} {{person.LastName}}
        </h4>
      </div>
      <div class="modal-body" style="overflow:auto">
        {% if site.data.institutions[person.Institution].name %}<div class="row">
          <div class="col-xs-2 ">Institution:</div><div class="col-xs-8 "><a target="_blank" href="{{site.data.institutions[person.Institution].homepage}}">{{site.data.institutions[person.Institution].name}}</a>, {{site.data.institutions[person.Institution].city}}</div>
        </div>{% endif %}
        {% if person.Job %}<div class="row">
          <div class="col-xs-2 ">Role:</div><div class="col-xs-8 ">{{person.Job}}</div>
        </div>{% endif %}
        {% if person.Email and person.ShowEmail%}<div class="row">
          <div class="col-xs-2 ">Email:</div><div class="col-xs-8 ">{{person.Email | downcase}}</div>
        </div>{% endif %}
        {% if person.Interests %}<div class="row">
          <div class="col-xs-2 ">Interests:</div><div class="col-xs-8 ">{{person.Interests}}</div>
        </div>{% endif %}
      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-default" data-dismiss="modal">Close</button>
      </div>
    </div>
  </div>
</div>
{% endfor %}
