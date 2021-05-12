---
title: "<br><br>quantum cryptography"
header:
  overlay_image: /assets/images/banner4.jpg
  overlay_filter: 0.2
  caption: ""
excerpt: '<br><br>'
toc: true
toc_sticky: true
toc_label: "quantum cryptography"
toc_icon: "key"
tags:
  - Pyton
  - JupyterLab
  - hardware
  - Docker
  - MQTT
  - cryptography
  - data science
  - security
categories:
  - project
last_modified_at: 2021-05-11 13:01
---

## the project

The goal of this project is to demonstrate quantum-cryptography-based one-time pad communication via
the BB84 protocol using a non-single photon source.

Check out the [git repository](https://github.com/bmedicke/quantum_cryptography) for more details, code, printable 3D models, and instructions.


## quantum key distribution

The basic order of events for the BB84 protocol are the following two steps:

1. generate a one time pad between Alice and Bob
2. check if anybody was eavesdropping

---

After sharing the key a test is performed: if anybody was listening the key is discarded,
if not they now have a new key to communicate with.  The reason why this works is because **any measurement on a quantum object leaves a trace**.
It is impossible to read information traveling over a quantum channel without perturbing it.

### BB84 protocol

The BB84 scheme can use any quantum object with a two value observable.
In practice the quantum object is the **polarization of a photon** (quantum optics).

#### prerequisites Alice

Alice has a source to generate photons with four possible polarizations:

1. **H**, horizontal
2. **V**, vertical
3. **L**, left
4. **R**, right

The four polarizations can be grouped into two sets.
The **HV set** is located along the X and Y axis. The **LR set** 45 degrees rotated from that.

#### prerequisites Bob

Bob has two polarization beam splitters with which he analyzes photons sent by Alice. One oriented at 0 degrees (vertical) and one at 45 degrees (diagonal).
The **vertical beam splitter** can analyze photons of the HV set. The **diagonal beam splitter** can analyze photons of the LR set.

Each beam splitter can produce two values.
* Vertical beam splitter:
  1. **H**, horizontal
  2. **V**, vertical
* Diagonal beam splitter:
  1. **L**, left
  2. **R**, right

To obtain the original value of a photon (without fail) the orientations of Alice and Bob have to match up. Some examples:

* inputting H into the vertical beam splitter will always return H (match)
* inputting V into the vertical beam splitter will always return V (match)
* **inputting L or R into the vertical beam splitter will return a random value (H or V, mismatch)**

#### procedure of events

For each (potential) bit of the key the following happens:

* Alice generates a randomly polarized photon (H, V, L or R) and publicly sends it to Bob
* Bob choses a random beam splitter to analyze the photon with
  * if Bob chose the correct beam splitter: he obtains the original value
  * if Bob chose the wrong beam splitter: he obtains a random value
* Bob saves the orientation of the beam splitter and the resulting value 
  * of which he still does not know if it's meaningful
  * there's a 50% chance it's just a random value due to orientation mismatch

After sending a bunch of photons we move on to the next step: **reconciliation**.

* Bob publicly announces all his chosen beam splitter orientations
* Alice publicly replies which were correct
* They both drop all the values where Bob chose wrong
* They now hold the key (which consists of all values where Bob chose correctly)

#### consequences of eavesdropping

If Eve intercepts a photon to measure it, Bob will not receive it and thus will not use it in the key.
Alternatively, Eve can retransmit a photon, but **Bob can detect this by sacrifing some
Bits of the key and publicly sending them back to Alice!**

_This is where the quantum nature of the transmission medium kicks in:_

* Eve does not know the correct orientation (vertical or diagonal) and thus has to guess
  * if Eve guesses correctly she has no problem
    * the orientations match up and Bob will get the correct value
  * if Eve guesses wrong there is a 50% chance that Bob will receive the wrong value
    * if Bob randomly chooses this Bit to sacrifice (and send it back to Alice) she has a problem indeed
* **Alice sees that Bob sent back a wrong value despite the correct orientation! The key cannot be trusted!**
  * any one Bit being wrong when eavesdropped will happen in about 25% of the cases
    * 50% chance that Eve chooses the wrong orientation set and 50% chance of that for a wrong value
