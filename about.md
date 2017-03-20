---
layout: page
title: The Experiment
---
<div class="container">
  <div class="row">

    <div class="col-sm-12 ">
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
    </div>
  </div>
</div>
<div id="circles" class="text-center">
  <h2>Find out more</h2>
  <div class="container">
    <div class="row">
      <div class='col-sm-4'>
<a href="#thephysics">
        <img src='assets/dbd_round.png' class="img-circle  center-block" style="width:17em">
        <h4>The physics</h4>
        <p class="lead">Learn about neutrinoless double beta decay</p>
        </a>
      </div>
      <div class='col-sm-4'>
        <img src='assets/detector_round.png' class="img-circle  center-block" style="width:17em">
        <h4>Our detector</h4>
        <p class="lead">See how the SuperNEMO demonstrator module works</p>
      </div>
      <div class='col-sm-4'>
        <img src='assets/status_round.png' class="img-circle  center-block" style="width:17em">
          <h4>SuperNEMO status</h4>
          <p class="lead">Find out how the project is going</p>
      </div>
    </div>
  </div>
</div>
<div class="container" id="thephysics">
  <div class="section_head text-center">
  <h2> The physics</h2>
</div>
<div class="row">
  <div class="col-sm-12 ">
    <h4> About neutrinos</h4>
    <p>Neutrinos, the light, uncharged cousins of electrons, are the second-most abundant particles in the universe, with millions of them streaming through your body every minute. But even though they are everywhere, they are some of the least understood particles that we know about. Neutrinos have no electric charge, and until recently, we thought they had no mass, as predicted by the Standard Model of particle physics. Now we know that they do have mass - though they are very light -  but we don't know how. Thanks to experiments looking at a phenomenon called neutrino oscillations, we are starting to learn more about them, but there is still a lot we don't know. What are their absolute masses? How did they get them? And as they are electrically neutral - could they be their own antiparticles? By looking for an extremely rare process called neutrinoless double beta decay, SuperNEMO hopes to answer some of those questions.</p>
  </div>
</div>

<div class="row">
<div class="col-sm-4 ">
<img src='assets/dbd_round.png' class="img-circle  center-block" style="width:17em">
</div>
<h4> Beta decay - two different kinds</h4>
<div class="col-sm-8 ">
  <p>There are many radioactive isotopes, with neutron-rich nuclei, that undergo beta decay. When this happens, a neutron in the nucleus decays to a proton, ejecting an electron ($\beta$ particle) and an electron-antineutrino. The resulting nucleus is more stable (has a lower energy). This 'lost' energy , $Q_\beta$, is shared between the electron and the neutrino.</p>
  <p>For a handful of isotopes, the nucleus resulting from a single decaying neutron would not be more stable, meaning $\beta$ decay is forbidden. However, if <em>two</em> neutrons decay at <em>the same time</em>, we do get a lower-energy nucleus, with an energy difference we call $Q_{\beta\beta}$. This decay is very rare, with a half-life longer than the age of the universe. It has been observed for 12 nuclei, by experiments including our predecessor NEMO-3. As it produces two beta electrons and 2 (electron-anti)neutrinos, we call it $2\nu\beta\beta$, a 2-neutrino double beta decay.</p>
</div>
</div>
<div class="row">
  <div class="col-sm-8 ">
    <h4>Neutrinoless double beta decay</h4>
    <p>This raises another possibility - what if neutrinos are their own antiparticles? (As with other electrically neutral particles, like the photon). In that case, in a $\beta\beta$ decay, the two antineutrinos could effectively annihilate, meaning our interaction produces only the two $\beta$ electrons, which carry the whole reaction energy $Q_{\beta\beta}$. This process is called neutrinoless double beta decay ($0\nu\beta\beta$), and so far, it has never been observed. SuperNEMO is trying to change that.</p>
    <p>If we see a $0\nu\beta\beta$ decay, that has big implications for physics. In 1937, Ettore Majorana proposed a mechanism whereby neutrinos are their own antiparticles - known as Majorana neutrinos. Observing a $0\nu\beta\beta$ decay would prove that the theory was true, explaining how neutrinos get their mass, and giving us clues as to how we live in a universe made only of matter, and not antimatter.</p>
</div>
<div class="col-sm-4 ">
<img src='assets/Ettore_Majorana.jpeg' class="img-circle  center-block" style="width:17em">
</div>
</div>
</div>
