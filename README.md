![Logo](admin/jeelab_logo.png)
# ioBroker.jeelink
![Number of Installations](http://iobroker.live/badges/jeelink-installed.svg) ![Number of Installations](http://iobroker.live/badges/jeelink-stable.svg) [![NPM version](http://img.shields.io/npm/v/iobroker.jeelink.svg)](https://www.npmjs.com/package/iobroker.jeelink)
[![Downloads](https://img.shields.io/npm/dm/iobroker.jeelink.svg)](https://www.npmjs.com/package/iobroker.jeelink)
[![Build Status](https://travis-ci.org/foxthefox/ioBroker.jeelink.svg?branch=master)](https://travis-ci.org/foxthefox/ioBroker.jeelink)

[![NPM](https://nodei.co/npm/iobroker.jeelink.png?downloads=true)](https://nodei.co/npm/iobroker.jeelink/)

This is an adapter for ioBroker to integrate RFM12B/RFM69 via a LaCrosseGateway.
The LaCrosseGateway documentation can be found at https://wiki.fhem.de/wiki/LaCrosseGateway_V1.x

## Installation:
### released version
```javascript
there is no production release right now
```
on raspberry it might help to use:
```javascript
there is no production release right now
 ```
### the actual development version from github (when under testing, may not work!)
```javascript
npm install https://github.com/verba03/ioBroker.jeelink/tarball/master --production
```
or
```javascript
npm install --unsafe-perm https://github.com/verba03/ioBroker.jeelink/tarball/master --production
```
## Settings:
- IP address of LaCrosseGateway
- IP port of LaCrosseGateway

## Configuration:
to be done in admin
* definition of the IP address
* setting the IP port
- define sensor address which is received on air
- define unique sensors address within adapter (LaCrosse changes the on air address after battery change, so observe the log and adjust the sensor address after battery change)
- define the type of sensor (see belows examples)
- define the room

## Sensors
|Object|device variants|telegram example|Description|
|--------|-------|:-:|--------|
|emonTH|emonTH|OK 19 ...|sensor from openenergy.org|
|emonWater|emonWater|OK 21 ... |sensor with RFM12B for water metering|
|LaCrosseDTH |TX|OK 9 ... |sensors from LaCrosse, technoline|
|LaCrosseDTT |TX|OK 9 ... |sensors from LaCrosse, technoline double temp|
|HMS100TF |TXH29DTH-IT|H00 ... |sensors technoline|
|LaCrosseBMP180||OK WS ... |sensor mod, LGW internal|
|LaCrosseBME280||OK WS ... |sensor mod, LGW internal|
|LaCrosseWS|WS1080,TX22,WS1600|OK WS ... |Weather Station|
|EC3000|EC3000|OK 22 ... |Energy Meter|
|EMT7110|EMT7110|OK EMT7110 ... |Energy Meter|
|level|level|OK LS ... |level sensor|

## TODO:
* other sensor types
* put the sensor code in separate file
* pushing new sensor to config, then visible in admin/config page
* HMS100TF Temp below 0°C and battery low to be implemented


## Changelog:
### 0.2.0
* first development release using LaCrosseGateway. Code based on adapter of foxthefox. Thanks.

### 0.1.3
* (atl285) added new sensor type LacCrosseDTT (double temp like TX25-IT)

### 0.1.2
* correction for weather (no data is given by value = 255)

### 0.1.1
* delete buffer function to be compatible with nodejs10
* enhanced automatic testing

### 0.1.0
* compact mode

### 0.0.7
* new level sensor (fhem)

### 0.0.6
* last version of serialport
* new sensor TXH29DTH-IT
* new weather station WS1600
* new sensor EC3000, EMT7110 not verified with life data

### 0.0.5
* adminv3 improved with values2table

### 0.0.4
* command to USB-stick for configuration
* added superjee, BMP180 sensor on jeenode
* admin v3 implementation

### 0.0.3
* abs humidity and dewpoint calculation

### 0.0.2
* definition of unique sensor ID for iobroker datapoint
* implementation of LaCrosseDTH
* definition of sensors via admin

### 0.0.1
* working with 3 sensors emon

## License

The MIT License (MIT)

Copyright (c) 2018 - 2020 foxthefox <foxthefox@wysiwis.net>
