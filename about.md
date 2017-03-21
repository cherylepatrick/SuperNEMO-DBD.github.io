---
layout: experiment
title: The Experiment
---

<div class="container" id="top">
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

<header class="post-header">
<h1 class="post-title text-center">The SuperNEMO experiment</h1>
</header>

<div id="circles" class="text-center">
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
        <a href="#detector">
        <img src='assets/detector_round.png' class="img-circle  center-block" style="width:17em">
        <h4>Our detector</h4>
        <p class="lead">See how the SuperNEMO demonstrator module works</p>
        </a>
      </div>
      <div class='col-sm-4'>
        <img src='assets/status_round.png' class="img-circle  center-block" style="width:17em">
          <h4>Physics goals</h4>
          <p class="lead">What SuperNEMO can tell us</p>
      </div>
    </div>
  </div>
</div>

<div class="container" id="thephysics">
  <div class="section_head text-center">
    <h2> The physics of SuperNEMO</h2>
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
<a href="">Back to top</a>
</div>

<div class="container" id="detector">
  <div class="section_head text-center">
      <h2> The SuperNEMO detector</h2>
  </div>
  <div class="row">
    <div class="col-sm-8">
      <img src="http://www.hep.ucl.ac.uk/nemo/images/Supernemo_module2.png" class="center-block" usemap="#detectormap">
        <map name="detectormap">
          <a  data-toggle="modal" data-target="#caloModal" title="Calorimeter wall" class="maphover calomap" style="position: absolute; left: 50%; top: 19.59%; width: 11.85%; height: 67.47%; z-index: 2;" ></a>
          <a data-toggle="modal" data-target="#caloModal" title="Calorimeter wall" class="maphover calomap"  style="left: 88%; top: 14.97%; width: 11.04%; height: 76.71%; "></a>
          <a data-toggle="modal" data-target="#caloModal"  title="Calorimeter wall" class="maphover calomap" style="left: 62%; top: 91.68%; width: 18.54%; height: 7.76%; "></a>
          <a data-toggle="modal" data-target="#trackerModal"  title="Tracker" class="maphover trackmap" style="left: 62.01%; top: 18.85%; width: 9.5%; height: 69.13%;"></a>
          <a data-toggle="modal" data-target="#trackerModal"  title="Tracker" class="maphover trackmap" style="left: 49.75%; top: 5.55%; width: 11.96%; height: 7.76%;"></a>
          <a data-toggle="modal" data-target="#trackerModal"  title="Tracker" class="maphover trackmap" style="left: 84.5%; top: 6.1%; width: 11.96%; height: 7.76%;"></a>
          <a data-toggle="modal" data-target="#trackerModal"  title="Tracker" class="maphover trackmap" style="left: 75%; top: 18.3%; width: 12.77%; height: 71.53%;"></a>
          <a data-toggle="modal" data-target="#trackerModal"  title="Tracker" class="maphover trackmap" style="left: 1.01%; top: 2.22%; width: 32.52%; height: 94.09%;"></a>
      </map>
    </div>
    <div class="col-sm-4 ">
      <p>The SuperNEMO detector has a tracker-calorimeter architecture, with a thin layer of $\beta\beta$-emitting isotope sandwiched between trackers and surrounded by calorimetry. This allows for a full three-dimensional reconstruction of charged particle tracks, as well as energy measurements. Click on the detector components in the diagram to learn more about each part of the detector.</p>
    </div>
  </div>
</div>


<!-- Calorimeter Modal -->
<div id="caloModal" class="modal fade" role="dialog">
  <div class="modal-dialog">
    <!-- Modal content-->
    <div class="modal-content">
      <div class="modal-header">
        <button type="button" class="close" data-dismiss="modal">&times;</button>
        <h4 class="modal-title">Calorimeter wall</h4>
      </div>
      <div class="modal-body" style="overflow:auto">
        <img src="assets/opticalmodule.png" alt="Optical module" style=" float:left; width:10em; padding: 5px;">
        <p>The calorimeter walls at the outside of the detector measure the energy of particles that reach the edge of the detector. The two main calorimeter walls consist of 520 optical modules. These are blocks of polystyrene scintillator coupled to 8” photomultiplier tubes and wrapped in teflon and mylar, with individual iron shielding.</p>
        
        <img src="assets/calowall.png" alt="Calorimeter wall" style=" float:right; width:15em; padding: 5px;">
        <p>There are also optical modules positioned above, below and to the sides of the tracker, giving a total of 712 modules. This allows SuperNEMO to measure particles' energies, whatever direction they travel in.</p>
      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-default" data-dismiss="modal">Close</button>
      </div>
    </div>
  </div>
</div>

<!-- Tracker Modal -->
<div id="trackerModal" class="modal fade" role="dialog">
  <div class="modal-dialog">
    <!-- Modal content-->
    <div class="modal-content">
      <div class="modal-header">
        <button type="button" class="close" data-dismiss="modal">&times;</button>
        <h4 class="modal-title">Wire tracker</h4>
      </div>
      <div class="modal-body" style="overflow:auto">
        <img src="assets/tracker_insert.png" alt="Optical module" style=" float:left; width:15em; padding: 5px;">
          <p>To track charged particles' progress across the detector, we use a wire-chamber tracker. On each side of the detector, we have 108 columns of nine drift cells, each consisting of a central anode wire surrounded by field shaping wires, with a ring-shaped cathode at either end. The tracker is filled with helium, with a small amount of ethanol and argon. When a charged particle passes through the cell, the time for the resulting electron shower to drift to the anode tells us the particle's distance from the centre of the cell. Pulses on the two cathode end caps tell us how far along the wire the particle was. In this way, we can reconstruct particles' tracks through the tracker in three dimensions.</p>
          
          <img src="assets/eventdisplay.png" alt="Two electron tracks in our event display" style=" float:right; width:15em; padding: 5px;">
            <p>The image shows two reconstructed electron tracks from a simulated $0\nu\beta\beta$ decay, taken from the SuperNEMO event display software. Each circle corresponds to one tracker cell. The blue blocks at the end of the tracks are calorimeter blocks, which we use to measure the particles' energy. The tracks are curved because we also simulate a 25G magnetic field. By using applying a magnetic field, we are able to tell the charge of a particle from the way its track curves.</p>

            </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-default" data-dismiss="modal">Close</button>
      </div>
    </div>
  </div>
</div>
