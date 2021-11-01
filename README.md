# dust_sensor
Raspberry PI and Arduino for dust sensor using SHARP light module

This project uses an arduino to communicate with the Wavshare dust sensor: this sensor uses a Sharp light emitter techology to be able to measure dust density.

We use an Arduino for reading the data from the sensor because the Raspberry does not have any ADC.

We want to use the Raspberry to read data from Arduino and do some "high level" code, maybe to store data into a Postgresql database and add a grafana on this.

Let's see where we can go! 


## Arduino Connections

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


## Installing / starting Postgresql on PI400 with Ubuntu 20.4 64 bits OS

Ya another difficult start... Anyway

install postgres

```sudo apt install postgresql```

then run it

```pg_ctlcluster 13 main start```


modify the file
```/etc/postgresql/13/main$ sudo nano pg_hba.conf```

with
```
# Database administrative login by Unix domain socket
local   all             postgres                                trust
```

Allowing lan connections requires modifying the config_file:

Find it with

```
psql -U postgres -c 'SHOW config_file'
```

then add 
```listen '*'```
for TCP/IP listening




stop pg and restart it
```
pg_ctlcluster 13 main stop
pg_ctlcluster 13 main start
```



log from the cli into postgres
define a password for the default user

```
psql -U postgres
ALTER user postgres with password 'postgres';

```






## Installing / Starting DBeaver on the PI

* Download the ARM version from (https://dbeaver.io/download/)[https://dbeaver.io/download/]
* unzip
* run the debeaver from the unzipped folder










