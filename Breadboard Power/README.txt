Breadboard Power
================
This is a power supply for a breadboard, providing +12V -12V and ground.

Power Capabilities
------------------
This consists of a standard half-wave rectifier circuit powered from 12 VAC
from a wall wart power supply. Since the 12VAC is powering both the +12VDC and
-12VDC rail, the total current requirements will be roughly the sum of the
current on both rails. The recommended 500mA wall wart will provide about
200-250mA per rail before degrading. There is also a 1000mA wall wart
available that would be able to provide more current. However, consider
carefully whether you actually want your breadboard, or any wires sticking out
of it, to be able to deliver enough current to catch components on fire.

If you want 15V out instead, this should be pretty easily configurable to
provide that. While I did not design it with 15V in mind, I think 15V can
generally be tuned without replacing any components other than the wall wart
power.

Noise and Precision
-------------------
This uses very high quality linear LDO regulators and an AC input, resulting
in extremely low ripple at 60Hz, without significant harmonic content at high
frequencies. I haven't done any robust measurements, but it seems to have
ripple within about 500uV at low loads, up to 1-2mV at high loads. So long as
the reservoir capacitor doesn't dip below the drop out ratings for the
regulators.

Compatibility and Location of the Rails
---------------------------------------
The power is put on the rails as follows:

-12 GND ... GND +12

As I have not seen any standard breadboard which is labeled this way, it is
recommended that you write over the +/- symbols on your breadboard with a
permanent marker.

This works with common 0.1" pitch breadboards. Note that AFAIK there is no
fixed standard for breadboards, so there is no guarantee it will work with any
particular breadboard. The most common incompatibility I've seen is where the
rail pins are not aligned with the main pins of the breadboard.

Safety
------
As a DIY project, I cannot possibly provide any guarantees that the finished
device will be safe. As with any electrical device, there is a small risk of
shock or fire under certain circumstances. Nevertheless, because it is
designed as a half-wave rectifier, overcurrents (shorts) tend to result in
both power rails rapidly dropping voltage, thus slowing the current's rise and
mitigating the effects. While there is no guarantee this will protect whatever
you futzed up, it has a greater chance of doing so than for a full-wave, high
power supply. Of course this is not as good as a properly current-limited
supply, but it acts similarly for a lot less money and complexity.

Ordering and Assembly
---------------------
I won't go into details here. Just a few notes.

* The large capacitors are 3300uF or 3.3mF. The capacitance and ESR is lightly
  related to efficiency and how close to the rated current you can go, but the
  exact value is not particularly important.

* The rectifier diodes are Schottkys, as otherwise the LDOs can get starved
  too easily. The voltage each diode sees is rail to rail at the supply
  capacitors, so don't skimp on a lower breakdown voltage.

* The LEDs are low current. If you change them, you will probably need to
  change the current limiting resistors as well.

