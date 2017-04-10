# OpenBilgeAlarm
An open source bilge water level alarm system 

## Requirements

It is important to comply with the regulations in SOLAS (International Convention for the Safety of Life at Sea), which means:

1. visual and audible alarm if bilges submerge with water
2. permanent check of the whole system and alert if sensor or wiring fails

### Environment

The system will work under moist conditions. The microcontroller can be located in the navigation room. Simple protection against dust and moisture will be sufficient. It is a dry and warm space. No need for any special casing. I would try to make it as a panel to be integrated into the board of all the other technical devices there. Ambient T is 10°C to 30°C. Humidity is rather high. Shock is low but may occur if some part may break and move inside the bilge (that is why I suggest having a cage around the sensor. i'll try to make a sketch or picture). Corrosion is high.


### Wiring

For our ship. I would count 35-40 meters of the bus backbone to the furthest sensor. From the backbone each sensor will need about 6-8 meters of cable. We have a cable channel along the side wall of the ship, where it will run along. Since the deepest parts of the sections will always be near the section walls, the backbone will be intersected there with the T-connectors.
So the furthest sensor should have something like 45m cable at max.

### Power

The ship runs on 24V DC batteries, which are charged and maintained externally. There is also a 220V AC inverter, but I prefer using the 24V DC and have a little converter for our needs. The maximum voltage we may have to consider is 29V in cases of charging with the generator. The minimum can get as low as 22.5V in case we are running really low on voltage.

But having a backup-battery will be a good idea anyways in case anything goes wrong with the other supplies?

## System architecture

 * A network of sensors is deployed on RS485 transport
 * [RS485-based soil moisture sensor](https://github.com/Miceuz/rs485-moist-sensor) is used
 * Central control system with user interface

### User interface

 * 2x16 character LCD
 * Rotary encoder w push button
 * Bright red alarm led
 * Multicolor status led
 * Buzzer
 * "Silence" button

