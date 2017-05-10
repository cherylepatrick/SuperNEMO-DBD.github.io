---
layout: page
title: The Collaboration
---

Who we are! Implement this page using, for example, [Jekyll data](http://jekyll.tips/jekyll-casts/data-files/)
so it's easy to keep the list updated and include relevant information.

<ul>
{% for person in site.data.people %}
<li>
<a data-toggle="modal" data-target="#{{person.Nickname}}_Modal">
{{ person.Name }}
</a>
</li>
{% endfor %}
</ul>


{% for person in site.data.people %}
<div id="{{person.Nickname}}_Modal" class="modal fade" role="dialog">
  <div class="modal-dialog">
    <!-- Modal content-->
    <div class="modal-content">
      <div class="modal-header">
        <button type="button" class="close" data-dismiss="modal">&times;</button>
        <h4 class="modal-title"><img src="{{person.Photo}}" alt="{{person.Name}}" class="img-circle" style="width:5em"> {{person.Name}}</h4>
      </div>
      <div class="modal-body" style="overflow:auto">
        <div class="row">
          <div class="col-xs-2 ">Institution:</div><div class="col-xs-8 ">{{person.Institution}}</div>
        </div>
        <div class="row">
          <div class="col-xs-2 ">Role:</div><div class="col-xs-8 ">{{person.Job}}</div>
        </div>
        <div class="row">
          <div class="col-xs-2 ">Email:</div><div class="col-xs-8 ">{{person.Email}}</div>
        </div>
        <div class="row">
          <div class="col-xs-2 ">Interests:</div><div class="col-xs-8 ">{{person.Interests}}</div>
        </div>
      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-default" data-dismiss="modal">Close</button>
      </div>
    </div>
  </div>
</div>
{% endfor %}
