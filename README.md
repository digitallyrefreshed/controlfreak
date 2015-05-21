# ControlFreak

## What is ControlFreak?
The goal of ControlFreak is to provide a modular system that can interact with control modules based on input from sensor modules. The system consists of one base module - ControlBox - that connects to the internet over Wifi ([Particle Photon][Photon]). This allows a user to specify triggers and actions that the base module acts upon. ControlBox also incorporates a Bluetooth Smart (BLE) module ([Rigado's BMD-200 SoC][BMD-200]) to connect to each available module. Each module contains the same BLE module and advertises its capability via DIS (Device Information Service). The base module connects to each sensor module at a module specific interval and requests any available data. Depending on the specified triggers the base module sends corresponding commands to control modules. Regular keep-alive messages ensure that each module is working and connected properly.

## What can ControlFreak be used for?
ControlFreak can be useful in many different scenarios. The initial concept was born out of the need to control a heat lamp for a backyard chicken coop. The idea was that if the coop temperature falls below a certain value a heat lamp would be turned on. Once the temperature rises above a certain value, the heat lamp would be turned off again.
Additional use cases could be:

* control a flood light based on ambient light and motion
* turn on motor or actuator based on proximity (e.g. door, feed dispenser, etc.)
* start video recording based on motion

## Modules
### Sensor Modules
Currently the following sensor modules are in development:

* temperature & humidity sensor module
* motion sensor

The following sensor modules are being thought of:

* ambient light sensor module
* weather station module (wind, rain, temperature, humidity, barometric pressure)
* bluetooth proximity module

### Control Modules
The following control modules are in development:

* 110V (AC) relay module with integrated power consumption monitor module

The following control modules are being thought of:

* DC motor driver module
* stepper motor/linear actuator driver module
* DC switch (relay) module (e.g. inputs to other devices)

## Internet Modules
In addition to physical modules, the following internet "modules" are available:

* sunrise/sunset times for given location (updated once per day)
* weather forecast for given location (updated hourly)

## Configuration & Updates
The system is configured via a web app or mobile app (iOS, Android at a later time). The mobile app will also handle OTA firmware updates of the sensor and control modules. The base module will update via the cloud.




[Photon]: http://www.particle.io/prototype#photon
[BMD-200]: https://www.rigado.com/product/bmd-200/
