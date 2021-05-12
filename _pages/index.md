---
layout: splash
permalink: "/"
classes:
  - landing
title: '<br><br>projects'
classes:
  - landing
header:
  overlay_color: "#000"
  overlay_filter: "0.2"
  overlay_image: /assets/images/banner2.jpg
excerpt: <br><br>

feature_row_drone_shots:
  - image_path: "assets/images/DJI_0786.jpg"
    alt: "drone shot: fuschl"
    excerpt: "<br>"
  - image_path: "assets/images/DJI_0052.jpg"
    alt: "drone shot: salzburg"
    excerpt: "<br>"
  - image_path: "assets/images/DJI_0082.jpg"
    alt: "drone shot: salzburg"
    excerpt: "<br>"

feature_row_quantum_cryptography:
  - url: "project/quantum-cryptography"
    title: "quantum cryptography"
    excerpt: "demonstration of quantum encrypted communication via the BB84 algorithm"
    btn_label: "read more"
    btn_class: "btn--light-outline btn--small"
  - image_path: "assets/images/IMG_0571.jpg"
    alt: "quantum cryptography: filter wheel"
    excerpt: "<br>"
  - image_path: "assets/images/Screenshot 2021-05-12 at 08.35.09.jpg"
    alt: "quantum cryptography: JupyterLab notebook of Alice"
    excerpt: "<br>"

feature_row_amalthea:
  - image_path: "assets/images/perlin-noise-01.jpg"
    alt: "amalthea: perlin noise"
    excerpt: "<br>"
  - url: "project/amalthea"
    title: "amalthea"
    excerpt: "various Notebooks for JupyterLab, creative coding exercises, demos and tutorials"
    btn_label: "read more"
    btn_class: "btn--light-outline btn--small"
  - image_path: "assets/images/speedtest00.jpg"
    alt: "amalthea: speedtest graph"
    excerpt: <br>

feature_row_reed:
  - url: ""
    title: "REED"
    excerpt: "collection of notes about reverse engineering and exploit development"
    btn_label: "read more"
    btn_class: "btn--light-outline btn--small"
  - image_path: "assets/images/stack-frame-main-function-prologue-a.jpg"
    alt: ""
    excerpt: "<br>"
  - image_path: "assets/images/payload-exit-in-memory-visual.jpg"
    alt: ""
    excerpt: <br>

feature_row_more_info:
  - image_path: "assets/images/auckland_marina.gif"
    alt: "arvakr: timelpase of the auckland marina"
    excerpt: <br>
  - image_path: "assets/images/cellular5.png"
    alt: "cellurar-automata-mapgen: 3D view"
    excerpt: <br>
  - url: "https://github.com/bmedicke"
    title: "more projects"
    excerpt: "<br>"
    btn_label: "github.com/bmedicke"
    btn_class: "btn--small btn--primary"

---

{% include feature_row id="feature_row_quantum_cryptography" %}
{% include feature_row id="feature_row_amalthea" %}
{% include feature_row id="feature_row_reed" %}

{% include feature_row id="feature_row_more_info" %}
{% include feature_row id="feature_row_drone_shots" %}
