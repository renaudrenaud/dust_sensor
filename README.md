# dust_sensor
Raspberry PI and Arduino for dust sensor using SHARP light module

This project uses an arduino to communicate with the Wavshare dust sensor: this sensor uses a Sharp light emitter techology to be able to measure dust density.

We use an Arduino for reading the data from the sensor because the Raspberry does not have any ADC.

We want to use the Raspberry to read data from Arduino and do some "high level" code, maybe to store data into a Postgresql database and add a grafana on this.

Let's see where we can go! 


## Connections

The Sharp sensor is very often sold with some 8 connectors and you have to add a resistor and a capacitor.
The Waveshare module save your time and patience, offering a back pack with 4 prins:
1. VCC
2. GND
3. AOUT - This is the analog out to read the measure
4. ILED - This pin is an input, allowing to control the LED inside the captor

Arduino / Sharp sensor connections:
* VCC   -   VCC
* GND   -   GND
* A0    -   AOUT
* D7    -   ILED
