# dust_sensor
Raspberry PI and Arduino for dust sensor using SHARP light module

This project uses an arduino to communicate with the Wavshare dust sensor: this sensor uses a Sharp light emitter techology to be able to measure dust density.

We use an Arduino for reading the data from the sensor because the Raspberry does not have any ADC.

We want to use the Raspberry to read data from Arduino and do some "high level" code, maybe to store data into a Postgresql database and add a grafana on this.

Let's see where we can go! 


