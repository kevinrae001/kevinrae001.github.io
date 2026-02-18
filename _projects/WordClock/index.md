---
layout: post
title: Word Clock
description:  I built a clock that tells the time in words. See github for the source code and detailed design.
skills: 
- C
- C++
- Arduino
- Soldering
- Power Management
- Maximizing chip usage
main-image: /banner.png
---

---
## The clock  
The project goal was to create an elegant looking clock that tells the time in words. Based on similar designs I've seen, I wanted to avoid: light bleeding, untidy wiring, using too many chips, and high cost.
{% include image-gallery.html images="WC1.png" %} 
The clock is a stripped down Arduino with just the atmega 328p microcontroller chip and the USB/serial interface. 
{% include image-gallery.html images="circuit_board_front.jpg" %} 
and
{% include image-gallery.html images="circuit_board_rear.JPG" %} 
I used charlieplexing to maximize the LEDs per pin while maintaing 100% brightness.
{% include image-gallery.html images="schematic1.png" %} 

Some more images:
Front display panel:
{% include image-gallery.html images="display_panel_front.JPG" %} 
Rear display panel:
{% include image-gallery.html images="display_panel_rear.JPG" %} 

I added a light sensor so the brightness could automatically adjust:
{% include image-gallery.html images="light_sensor.JPG" %} 

This is what the finished backside looked like:
{% include image-gallery.html images="rear.JPG" %} 





