Breadboard Power
================
This is a power supply for a breadboard, providing +12V -12V and ground. It is
designed to be robust, simple, repairable, and safe.

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

Noise and Precision
-------------------
This uses high quality linear LDO regulators and an AC input, resulting
in low ripple at 60Hz, without significant harmonic content at high
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
device will be safe. As with any unshielded electrical device, there is a small
risk of shock or fire under certain circumstances.

Nevertheless, this power supply is designed with safety and robustness in mind.
Resettable fuses placed between the reservoir capacitors and the regulators
will clamp down on overcurrents and shorts. If you trip them, unplug it, count
to 10, and plug it back in. Additionally, the regulators themselves have
internal current limiters that might catch on before the fuses. Additionally,
there are zeners to prevent overvoltage, which, depending on how bad the
overvoltage is, will trip those same fuses. And of course the power itself is
coming from the isolated secondary of a transformer.

Ordering and Assembly
---------------------
I won't go into details here. Just a few notes.

* The large capacitors are 3300uF or 3.3mF. The capacitance and ESR is lightly
  related to efficiency and how close to the rated current you can go, but the
  exact value is not particularly important.

* The rectifier diodes are Schottkys, as otherwise the LDOs can get starved
  too easily. The voltage each diode sees is rail to rail at the supply
  capacitors, so don't skimp on a lower breakdown voltage.

* The LEDs are low current, and the resistors into them give very low current,
  resulting in just enough brightness so you can tell that they're on. This
  "barely on" is intentional behavior to lower eye strain when looking at the
  breadboard, but if you want them to be brighter, just lower the value of the
  resistors by half or so. Note that if you substitute higher current LEDs, you might need
  lower value resistors for the LEDs to be visible at all.
