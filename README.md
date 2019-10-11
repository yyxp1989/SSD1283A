# SSD1283A for Arduino

This library supports SSD1283A to use with Adafruit_GFX and/or LCDWIKI_GUI.

The code is extracted from LCDWIKI_SPI and adapted for single controller use and Adafruit_GFX.

Only HW SPI is supported.

### General Remark

The SSD1283A controller seems to have an issue with data entry modes.
Only Mode 3 seems to work correctly, with both AM directions.

Graphics drawing works with all 4 rotation directions, as far as tested (pushing same color).
Bitmaps drawing, e.g. for canvas, using pushColors, works only correctly for rotation 0 and 3.
Use rotation for drawing to the canvas, but use rotation 0 or 3 for pushing the canvas to screen.

### Version 1.0.0
- improved rotation somewhat, see general remarks
- fixed clipping (drawPixel, fillRect)
- optimizations and cleanup
#### Version 0.0.6
- fixed rotation
#### Version 0.0.5
- fast pushColors() optimized also for Teensy 3.2
- cleaner implementation of fast pushColors()
#### Version 0.0.4
- fix some copy/past or replace errors
#### Version 0.0.3
- added example graphicstest_through_canvas.ino
- added faster pushColors() method, optimized for ESP32, ESP8266
#### Version 0.0.2
- fixed SPI transaction nesting issue, causing hang on ESP32 and other platforms
- still a preliminary version
#### Version 0.0.1
- initial preliminary version for initial check-in
- works with my "Transflective Display Module LCD Display DIY SPI Serial Port 130*130 Communicate for Arduino"
- https://www.aliexpress.com/item/4000116854157.html
- rotation does not work correctly