---
layout: page
title: The Collaboration
---

Who we are! Implement this page using, for example, [Jekyll data](http://jekyll.tips/jekyll-casts/data-files/)
so it's easy to keep the list updated and include relevant information.

<ul>
  {% assign sorted_people = (site.data.people | sort: 'LastName') %}
  {% for person in sorted_people %}
  <li>
    <a data-toggle="modal" data-target="#{{ person.FirstName }}{{ person.LastName }}_Modal">{{ person.FirstName | capitalize}} {{ person.LastName | capitalize}}</a>
  </li>
  {% endfor %}
</ul>

{% for person in site.data.people %}
<div id="{{ person.FirstName }}{{ person.LastName }}_Modal" class="modal fade" role="dialog">
  <div class="modal-dialog">
    <!-- Modal content-->
    <div class="modal-content">
      <div class="modal-header">
        <button type="button" class="close" data-dismiss="modal">&times;</button>
        <h4 class="modal-title">
          {% if person.Photo %}
            <img src="{{person.Photo}}" alt="Picture of {{person.Name}}" class="img-circle" style="height:5em">
          {% endif %}
          {{person.FirstName| capitalize}} {{person.LastName| capitalize}}
        </h4>
      </div>
      <div class="modal-body" style="overflow:auto">
        {% if person.Institution %}<div class="row">
          <div class="col-xs-2 ">Institution:</div><div class="col-xs-8 ">{{person.Institution}}</div>
        </div>{% endif %}
        {% if person.Job %}<div class="row">
          <div class="col-xs-2 ">Role:</div><div class="col-xs-8 ">{{person.Job}}</div>
        </div>{% endif %}
        {% if person.Email %}<div class="row">
          <div class="col-xs-2 ">Email:</div><div class="col-xs-8 ">{{person.Email}}</div>
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
