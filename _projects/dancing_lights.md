---
layout: page
title: Dancing Lights
description: visualization of sound using LEDs
img: assets/img/audio/IMG_20141207_041344.jpg
importance: 3
category: audio
related_publications: false
---

This was a project for one of my classes at UC Berkeley, EE 40: Introduction to Microelectronic Circuits. At the end of the semester we were given the opportunity to devise our own lab project. Purpose of the project is to create an active bandpass filter that relates amplitude of sound to number of LEDs that are lit up. Circuitry, detailed below, has the following chain of events:
- Signal from piezoelectric microphone is conditioned to fall between 0-3V with a DC offset of +1.65V
- Conditioned signal enters a Sallen-Key High Pass Filter to remove DC offset, along with other low freq signals, and magnify signal to +/-9V
- Signal goes through Sallen-Key Low Pass filter to chop off high frequency content
- Signal goes to a final op amp with variable gain using a potentiometer which is activated using a button switch
- Final signal goes to voltage divider which evenly divides the amplitude of signal into 4 sections
- Each point of division is forked into an op amp with unity gain, to prevent leakage current, that drives two LEDs with a BJT



<div  class="container-fluid" align="center" >
    {% include video.liquid path="https://www.youtube.com/embed/awmV00ETr7M?si=WUVZCxuxG9_usKqH" width="560" height="315" title="YouTube video player" max-width="100%" class="embed-responsive-item youtube rounded z-depth-1" %}
</div>

<div class="caption">
    Demo of circuit reacting to song "Light Pollution" by Lifeformed. Song from the game Dustforce.
</div>


<div class="row" align="center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/audio/amp.png" title="example image" width="33%" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Initial amplification and conditioning of signal that feeds into custom circuitry below.
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/audio/Dancing-Lights.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Schematic of filter and drive circuitry.
</div>

<div class="row align-items-center">
    <div class="col-sm mt-2 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/audio/original.jpg" title="example image" class="img-fluid rounded z-depth-1" zoomable="true" %}
    </div>
    <div class="col-sm mt-2 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/audio/IMG_20141208_205208.jpg" title="example image" class="img-fluid rounded z-depth-1" zoomable="true" %}
    </div>

</div>
<div class="caption">
    On the left is initial breadboard creation as a result of a few labs. On the right on can see extra circuitry created to achieve "Dancing Lights" portion on long breadboard.
</div>