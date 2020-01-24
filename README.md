# OctoPrint Filament Scale

This plugin allows connecting an HX711-based load cell to Octoprint to read out the current weight of the remaining filament.

You will need an HX711 breakout board and a compatible load cell. You can find these bundled together on Ebay/Aliexpress for roughly $8. Any load cell rated for more than 1kg and less than 50kg should work; I used a 5kg load cell with solid results.

See here for instructions on wiring up the load cell: https://tutorials-raspberrypi.com/digital-raspberry-pi-scale-weight-sensor-hx711/

The four cables of the Load Cell must be connected to the weight sensor. The green HX711, however, has six connections, of which we only need four for the cables. The connection is as follows:
Red: E+
Black: E-
Green: A-
White: A+
The pins labeled B+/B- remain empty. Apparently there are versions of the sensor. Where the pins are labeled S+/S- instead of A+/A-.
Now you just have to connect the sensor to the Raspberry Pi. Since this also has only four connections, the wiring is quite simple:
VCC to Raspberry Pi Pin 2 (5V)
GND to Raspberry Pi Pin 6 (GND)
DT (data) to Raspberry Pi Pin 38 (GPIO 20)
SCK (clock) to Raspberry Pi Pin 40 (GPIO 21)

This plugin assumes you connected the data pin to GPIO20, and the clock pin to GPIO21.


## Setup

Install via the bundled [Plugin Manager](https://github.com/foosel/OctoPrint/wiki/Plugin:-Plugin-Manager)
or manually using this URL:

    https://github.com/dieki-n/OctoPrint-Filament-scale/archive/master.zip


## Configuration

Once you have wired up the HX711, it must be calibrated. This is a pretty straightforward process, and all you will need is an object of known weight. Attach the load cell to your printer with the printed bracket, then follow the instructions on the plugin's settings page.

