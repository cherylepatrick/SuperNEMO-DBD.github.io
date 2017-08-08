---
layout: home
---

<div class="container-fluid" id="top">
  <div class="row">
    
    <div class="col-xs-9">
      <div id="carousel-example-generic" class="carousel slide" data-ride="carousel" style=" width:100%;">
        <!-- Wrapper for slides -->
        <div class="carousel-inner">
          {% for slide in site.carousel_images %}
          <div class="item {% if forloop.first == true %} active {% endif %}">
            <div style="background:url({{slide.image_url}}) center center; background-size:cover;" class="slider-size">
              <div class="carousel-caption" {% if slide.text_colour %}style="color:{{slide.text_colour}}"{% endif %}>
                <h4>{{slide.title}}</h4>
                {{slide.detail}}
              </div>
            </div>
          </div>
          {% endfor %}
        </div>
        <!-- Controls -->
        <a class="left carousel-control" href="#carousel-example-generic" role="button" data-slide="prev">
          <span class="glyphicon glyphicon-chevron-left" aria-hidden="true"></span>
          <span class="sr-only">Previous</span>
        </a>
        <a class="right carousel-control" href="#carousel-example-generic" role="button" data-slide="next">
          <span class="glyphicon glyphicon-chevron-right" aria-hidden="true"></span>
          <span class="sr-only">Next</span>
        </a>
      </div>
      
      <br/>
      <h1 class="post-title">Searching for Neutrinoless Double Beta Decay</h1>
    </div>
    
    <div class="col-xs-3">
      <img src="assets/supernemo_logo_v1.0.png" style=" width:100%;"/>
      <hr/>
      <p>How about a SuperNEMO presentation or poster at your conference?</p>
          <div class="boxbutton">
            <a href="mailto:lang@PHYSICS.UTEXAS.EDU?Subject=Request%20for%20SuperNEMO%20speaker" target="_top">
            <div class="content">
              <div class="table">
                <div class="table-cell">
                  Request a NEMO speaker
                </div>
              </div>
            </div></a>
          </div>
    </div>
  </div>
</div>
