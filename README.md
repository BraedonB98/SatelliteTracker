# SatelliteTracker

A satellite tracker for radio communications

## Purpose

This project is meant to allow for the downlink of noaa satellites and upload imaging to the internet/database on a budget. With the use of arduino, tv antennas, and stepper motors it will allow for a DIY approach to downlinking from satellites.

## Project Structure

### Coding

#### Frontend

The front end will allow for a nice GUI to see satellite downlink information. This includes displaying , where satellites are currently located, when the next pass will be, what the last image downlink was, where the user is located. They will also be able to change antenna settings, satellite settings, location settings, rotator settings, image settings, ext. With out requiring the changing of code.

#### Backend

Will work with different apis to both control the rotor, allow for sensor readings and imaging information to be passed onto the front end

#### Satellite Location and Orientation API

This API will get a request with a satellite,location, and time and will give the relative elevation and azimuth of the satellite relative to the user at the specified time(also potentially generate a path). This API will also periodically automatically update the tle files from another API (I did not write) to maintain as accurate of info as possible

#### Antenna Positioning API

This API will generate a path the satellite is going to travel and then pass the information to the arduino

#### Arduino Sensor

With current designs there is a sensor payload located on the back of the rotator with information like gyro, compass, barometer, gps, temperature. This software will take in readings from all of these devices and pass it onto another piece of software

#### Arduino Rotator

With current designs there is a separate arduino driving the stepper motors. This software will allow for the input of the back end to move the antenna right, left, up, and down, specified amounts.

#### SDR

This software will interface with the Software defined radio. Allowing for the backend to change the radios receiving frequency, and other settings. While also passing information about received information from transmission to the backend.

#### NOAA Image Processing

This will use WXTOIMG or software similar to it to take the "audio" noise received the the sdr and decode it into an image(s) and data to be returned

### Mechanical & Electrical

#### Antenna/SDR

all antenna and sdr information and data sheets

#### Sensor Payload

bill of materials, wire diagrams, part assemblies

#### Rotator

bill of materials, wire diagrams, part assemblies

## Resources/References

### API's

#### Satellite location

TLE API - https://tle.ivanstanojevic.me/

#### Satellite display

Google earth - https://developers.google.com/earth-engine

### Reference/Learning Material

Satellite position calculation based on TLE - https://space.stackexchange.com/questions/58041/how-to-calculate-azimuth-elevation-of-a-satellite
Google Earth NPM Installation documentation - https://developers.google.com/earth-engine/guides/npm_install
NodeJS Arduino Integration - https://medium.com/@svsh227/nodejs-with-arduino-5020489f3ec7

### Projects used

Pan Tilt Stepper Motor Gimbal - https://www.thingiverse.com/thing:4316563 (isaac 879)

### Disclosures

This software is not meant to be used for commercial purposes. There shall not be any expectation that the software was, is, or will be in a working condition. This is a ongoing project and none of the developers or any other entities are responsible for any damages that come from running software or hardware. The user accepts responsibility and sole liability to prevent injury or death from the rotator or any other hardware from the use of this project or any subsequent projects.
