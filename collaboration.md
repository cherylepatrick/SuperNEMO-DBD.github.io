---
layout: page
title: The Collaboration
---

SuperNEMO is an international collaboration comprising physicists and engineers from across Europe and beyond.
<div class="container-fluid">
  {% assign sorted_insts = (site.data.insts | sort: 'name')%}
{% for inst in sorted_insts %}
<hr/>
<div class="row">
  <div class="col-xs-3 ">
    <a target="_blank" href="{{inst.homepage}}"><img src="{{inst.logo }}"
      alt="{{inst.name }} logo"
      style="width: 100%">
      {{inst.name}}, {{inst.city}}</a>
  </div>
  
  {% assign sorted_people = ((site.data.people | where: "Institution", inst.shortname | sort: 'LastName') %}
  {% if sorted_people.size < 5 %}
    <div class="col-xs-8 ">
    {% for person in sorted_people %}
    <p>    <a data-toggle="modal" href="#{{ person.FirstName  | slugify}}{{ person.LastName  | slugify}}_Modal">{{ person.FirstName }} {{ person.LastName}}</a> </p>
    {% endfor %}
  </div>
  {% else %}
  <div class="col-xs-4 ">
    {% for person in sorted_people %}
    {% assign doubled = forloop.index0 | times:2  %}
    {% if  sorted_people.size > doubled  %}
    <p>    <a data-toggle="modal" href="#{{ person.FirstName  | slugify}}{{ person.LastName  | slugify}}_Modal">{{ person.FirstName }} {{ person.LastName}}</a> </p>
    
    {% endif %}
    {% endfor %}
  </div>
  <div class="col-xs-4 ">
    {% for person in sorted_people %}
    
    {% assign doubled = forloop.index0 | times:2  %}
    
    {% if sorted_people.size <= doubled %}
      <p>    <a data-toggle="modal" href="#{{ person.FirstName | slugify}}{{ person.LastName | slugify}}_Modal">{{ person.FirstName }} {{ person.LastName}}</a> </p>
      {% endif %}
      {% endfor %}
      </div>
  {% endif %}
  
</div>
{% endfor %}
</div>


{% for person in site.data.people %}
<div id="{{ person.FirstName | slugify}}{{ person.LastName | slugify}}_Modal" class="modal fade" role="dialog">
  <div class="modal-dialog">
    <!-- Modal content-->
    <div class="modal-content">
      <div class="modal-header">
        <button type="button" class="close" data-dismiss="modal">&times;</button>
        <h4 class="modal-title">
          {% assign inst = (site.data.insts | where: "shortname", person.Institution | first) %}
          {% if person.Photo %}
            <img src="{{person.Photo}}" alt="Picture of {{person.Name}}" class="img-circle" style="height:5em">
          {% elsif inst.logo %}
            <img src="{{inst.logo }}"
              alt="{{inst.name }} logo"
              style="height:3em">
          {% else %}
            <img src="assets/supernemo_logo_v1.0.png" alt="SuperNEMO logo" style="height:3em">
          {% endif %}
          {{person.FirstName}} {{person.LastName}}
        </h4>
      </div>
      <div class="modal-body" style="overflow:auto">
        {% if inst.name %}<div class="row">
          <div class="col-xs-2 ">Institution:</div><div class="col-xs-8 "><a target="_blank" href="{{inst.homepage}}">{{inst.name}}</a>, {{inst.city}}</div>
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
