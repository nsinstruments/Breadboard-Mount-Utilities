Voltage Source
==============
This is a breadboard mounted dual precision voltage source, switchable between
0V, 3V, and 5v. It is designed to work with the breadboard mounted power
supply in this repository.

Power and Compatibility
-----------------------
This is designed to be powered by breadboard rails with the following
voltages:

-12 GND ... GND +12

This works with common 0.1" pitch breadboards. Note that AFAIK there is no
fixed standard for breadboards, so there is no guarantee it will work with any
particular breadboard. The most common incompatibility I've seen is where the
rail pins are not aligned with the main pins of the breadboard.

Calibration
-----------
This uses precise voltage sources and potentiometers to calibrate an output
voltage to very exact standards, within half a millivolt or so. You can
momentarily get better (within 10 microvolts), but this won't necessarily
stick around with with the mechanical settling of the trimmers or with
temperature changes. The resulting voltage will only be as accurate as your
multimeter, so make sure your multimeter will measure according to your
requirements. Go through each voltage one at a time, and turn the appropriate
potentiometer until the output is satisfactorily close to the nominal value.
You may get better accuracy by going through each voltage a second time, as
the voltage sources may shift very slightly with a slightly changing load.
This will also give the parts time to warm up to their typical operating
temperature. You might need to recalibrate as the trimmers settle.

Accuracy
---------
After calibration, there are three significant remaining sources of
inaccuracy. First, the voltage references themselves contribute a small
temperature dependency of 50ppm per degree C (or whatever is specified for the
particular part you are using). This figure is multiplied by the ratio of the
output voltage to the reference voltage (2.5V). Second, the potentiometers
contribute a temperature dependency. Last, the op amp offset and bias current
both have a temperature dependency. The op amp offset change with temperature
will be reproduced multiplied by the ratio of the output voltage to the
reference voltage. The op amp bias change with temperature will be reproduced
multiplied by the very large source resistors, so it is highly recommended
that you only use FET input op amps.

Resistor values
---------------
The calibration range is set by a resistor in series with the wiper of each
trimmer. You may get better results by using larger resistors. The current
values are chosen to ensure you can calibrate even with inaccurate resistors
and a TL072 op amp. With the suggested OPA2162 op amp, you should be able to
raise these values a bit, if you find that necessary for your requirements.
Regardless, you probably want to use the highest value resistor you have for
the 0V reference; 4.7M as indicated is probably sufficient but even with a lot
of other errors 10-20M shouldn't pose a problem for calibration.
