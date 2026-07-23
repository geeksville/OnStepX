

## Seting up web
Default SSID is OnStepX, password is "password".  It will serve its webpage from http://192.168.0.1
OnstepX is version 10.24c

## 3d printed panels

Based on the excellent existing models - but tweaked to fit the RA brake and not require metal inserts for threads.  Editable [here](https://cad.onshape.com/documents/fcc42821c80392797101e68e/w/b736561701c3a8da688b9f02/e/3aa2c8209cb73604b21e2f7d?renderMode=0&uiState=6a6281e563834c4461102bc8), or the STLs are [here](juwei).

## Building the firmware

** VERY IMPORTANT *** 
Newer ESP32 Arduino library, downgradeESP32 Expressif library to version 2.0.17. If you don't do this the motors just hum - they
don't actually move.  Also be very careful to use the other specific versions mentioned in the Onstep E4 link below.

## wiring

* The stock Juwei steppers just plug into the E4 board with no need for pin swapping.
* plug the old power switch into XMIN - so it can serve as an emergency stop button
* attach GPS to YMIN (signal to GPS TX, gnd to gnd).  Attach GPS Vcc to any of the 5V pins on the board
* Cut the connector off of the 'brake' cable and hook the brake wires to the +/- "HEATER" output - which is reconfigured in firmware
be brake enable.
* Connect the power connector to the two +/- Power in screw terminals.

## ASCOM driver

Use version 1.0.40 of the ascom driver - 1.0.43 seems to not connect to the serial port: http://stellarjourney.com/main/onstep-ascom-driver-software/

## Hand controller

The stock juwei hand controller can probably be reflashed with https://onstep.groups.io/g/main/wiki/7152 to control the E4 via wifi instead of the ST4 port.  But I haven't investigated/bothered.

* Original awesome post https://www.cloudynights.com/forums/topic/918425-juwei-17-mounts-on-aliexpress/page/47/#findComment-14059463
* Old E4 firmware branch info https://onstep.groups.io/g/main/wiki/32794
* General onstep firmware info https://onstep.groups.io/g/main/wiki/32776
* Onstep Fysetc E4 info https://onstep.groups.io/g/main/wiki/32747
* E4 mfg wiki https://wiki.fysetc.com/docs/E4
* mfg gpio assignments https://github.com/FYSETC/FYSETC-E4
* Used this GPS module: https://www.amazon.com/Coliao-GY-NEO6MV2-NEO6MV2-Control-Antenna/dp/B0DBPTWY8J
* with GPS antenna recommended 7cm ground plane https://avrproject.ru/EB-500/GPS_Antennas_ApplicationNote-GPS-X-08014-.pdf
* why longitude is inverted https://onstep.groups.io/g/main/topic/negative_longitude_values/99160170

misc notes 
old gps on com1 or com3
focuser/flat panel is com12/13?
new mount is com11
