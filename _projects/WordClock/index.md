---
layout: post
title: "Word Clock"
description: "A wall clock that tells the time in words, built around a bare ATmega328P with charlieplexed LEDs and automatic brightness control."
skills:
  - C
  - C++
  - Arduino
  - Embedded Electronics
  - Soldering
  - Charlieplexing
  - Power Management
main-image: /banner.png
---

{% include image-gallery.html images="WC1.png" height="520" %}

## The build

The goal was to build an elegant, readable word clock while avoiding common pitfalls:

- **Light bleeding** between words
- **Messy wiring** and bulky electronics
- **Too many driver chips** / wasted MCU I/O
- **Unnecessarily high cost**

## How it works

At its core, this is a stripped-down Arduino design: just the ATmega328P (DIP package) with a USB/serial interface for programming, and a quartz crystal + trim capacitor for timekeeping.

The display is driven with charlieplexing to maximize the number of LEDs per pin while keeping 100% brightness (no multiplex dimming).

{% include image-gallery.html images="circuit_board_front.jpg, circuit_board_rear.JPG" height="380" %}

## Electronics and I/O optimization

Charlieplexing lets you drive many LEDs with fewer pins by exploiting tri-state I/O (HIGH / LOW / Hi-Z). This design choice kept the circuit simple and minimized extra components.

{% include image-gallery.html images="schematic1.png" height="520" %}

## Display panel and light control

To prevent light bleed and keep the face clean, the display uses a segmented/baffled panel to isolate each word area.

{% include image-gallery.html images="display_panel_front.JPG, display_panel_rear.JPG" height="420" %}

A photoresistor on the frame enables automatic brightness adjustment based on ambient light.

{% include image-gallery.html images="light_sensor.JPG" height="420" %}

## Assembly and packaging

Final internal layout (including the controller module and power setup):

{% include image-gallery.html images="rear.JPG" height="520" %}

---

### Links

- Code / firmware: https://github.com/kevinrae001/Word_clock
