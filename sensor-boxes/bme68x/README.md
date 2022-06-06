# Sensor Boxes

The sensor box STL is for a small sensor box designed to house:
* 1x [Adafruit QT Py ESP32-C3 WiFi Dev Board](https://learn.adafruit.com/adafruit-qt-py-esp32-c3-wifi-dev-board);
* 1x [Adafruit BME688 - Temperature, Humidity, Pressure and Gas Sensor - STEMMA QT](https://www.adafruit.com/product/5046).

An interconnecting STEMMA QT cable will need to be 'wound' gently (a small loop should appear).

The second STL is for extra parts in the event you mess up a print, or got creative with trying to increase ventilation (or broke the BME68x mounts).

## Construction

The core sensor box is the large structure.  The lid is the flat (and now vented) structure.  The 'window slot lock' is the rectangular slot with a window cut out of it.  The 'BME68x mounts' are slot mounts for holding the BME688 (or BME680, hopefully!).

* The ESP32-C3 QT Py slides into the slide rails towards the USB-C hole; it should sit nicely in the hole;
* Push the window slot lock down between the vertical rails behind the board, there should be enough clearance in both width and depth to pin the board in place, with the QT connector exposed in the window;
* Connect your QT cable to the ESP32-C3 QT port;
* Connect the other end of the QT cable to the sensor board (BME688; or BME680 if it fits).  I prefer the LED to be positioned top right, but you can change this as you wish (it will be top right or bottom left; it is next to the Adafruit star;
* Gently rotate the sensor board a full 360 degrees to create a loop (25mm cables will have one loop);
* Slide at least one BME68x mount into the screw mounting holes on the sensor board (I only use the top because I find it's enough; I print both in the event one breaks from the print bed -- they're fragile!);
* Align the BME68x mount(s) with the rails in the rear/top of the case;
* Slide the rails into place carefully.  You may need to gently bend the pins into the holes in the base (depending on the precision of your printer);
* Slide the vented lid into the top slot with the vent at the top (over the sensor board).

## Calibration

Calibration of the BME680 and BME688 is a little weird.  Generally speaking there will be a temperature offset of anywhere between 2 and 8 degrees from reference sensors.  Once appropriately calibrated (per the BME688 documentation) you may still need to set the ambient temperature setting differently.  Part of the issue will be a self-heating issue from the gas sensor in the BME68x; part of the issue will be PLA providing weak heat transfer.

Options to reduce the heat transfer include introducing further holes in the back of the case, but I've found it easier (in my use case) to just calibrate the temperature sensors and to store the data on the board.  If you're stuck, use a QT <-> Raspberry Pi adapter and use one of the various guides on calibration.