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
excerpt: "<br><br>"

feature_row_1:
  - image_path: assets/images/DJI_0786.jpg
    alt: "drone shot: fuschl"
    excerpt: "<br>"
  - image_path: assets/images/DJI_0052.jpg
    alt: "drone shot: salzburg"
    excerpt: "<br>"
  - image_path: assets/images/DJI_0082.jpg
    alt: "drone shot: salzburg"
    excerpt: "<br>"

feature_row_2:
  - url: http://localhost:4000/project/quantum-cryptography/
    title: Quantum Cryptography
    excerpt: 'demonstration of quantum encrypted communication via the BB84 algorithm'
    btn_label: "read more"
    btn_class: "btn--light-outline btn--small"
  - image_path: assets/images/IMG_0571.jpg
    alt: "quantum cryptography: filter wheel"
    excerpt: "<br>"
  - image_path: "assets/images/Screenshot 2021-05-12 at 08.35.09.jpg"
    alt: "quantum cryptography: JupyterLab notebook of Alice"
    excerpt: "<br>"

---

{% include feature_row id="feature_row_1" %}

{% include feature_row id="feature_row_2" %}
