Function Generator
==================
This is a simple breadboard mounted dual function generator, with a range of
3.5 minute cycles to 20kHz and a triangle and square wave output. It is
designed to work with the breadboard mounted power supply in this repository.

Power and Compatibility
-----------------------
This is designed to be powered by breadboard rails with the following
voltages:

-12 GND ... GND +12

This works with common 0.1" pitch breadboards. Note that AFAIK there is no
fixed standard for breadboards, so there is no guarantee it will work with any
particular breadboard. The most common incompatibility I've seen is where the
rail pins are not aligned with the main pins of the breadboard.

Notes on Components
-------------------
* The ceramic capacitors used in the oscillator must be C0G/NP0, but could be
  replaced by film capacitors if they match the footprint.
* The electrolytic capacitors used in the oscillator are bipolar. Unlike in a
  decoupling application, in this circuit a polarized electrolytic would fail,
  possibly rupturing violently.
