---
layout: page
title: The Collaboration
---

SuperNEMO is an international collaboration comprising physicists and engineers from across Europe and beyond.
<div class="container-fluid">
{% for inst in site.data.institutions %}
  <hr/>
  <div class="row">
    <div class="col-xs-3 ">
      <a target="_blank" href="{{inst[1].homepage}}"><img src="{{inst[1].logo }}"
        alt="{{inst[1].name }} logo"
        style="width: 100%">
        {{inst[1].name}}, {{inst[1].city}}</a>
    </div>
    <div class="col-xs-9 ">
      {% assign sorted_people = ((site.data.people | where: "Institution", inst[0]) | sort: 'LastName') %}
      {% for person in sorted_people %}
        <p>    <a data-toggle="modal" href="#{{ person.FirstName }}{{ person.LastName }}_Modal">{{ person.FirstName }} {{ person.LastName}}</a> </p>
      {% endfor %}
    </div>
  </div>
{% endfor %}
</div>




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
