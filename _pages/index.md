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
    excerpt: "collection of Notebooks for JupyterLab, creative coding excercises and various demos and tutorials"
    btn_label: "read more"
    btn_class: "btn--light-outline btn--small"
  - image_path: "assets/images/speedtest00.jpg"
    alt: "amalthea: speedtest graph"
    excerpt: <br>

---

{% include feature_row id="feature_row_quantum_cryptography" %}

{% include feature_row id="feature_row_amalthea" %}

{% include feature_row id="feature_row_drone_shots" %}
