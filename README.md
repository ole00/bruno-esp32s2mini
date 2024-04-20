# bruno ESP32-S2-Mini 
Break-out board for ESP32-S2-Mini to Arduino UNO style base board.
![Board image](https://github.com/ole00/bruno-esp32s2mini/raw/master/img/bruno-esp32s2mini.jpg "bruno-esp32s2mini")

This PCB allows you to experiment with various Arduino 3.3V compatible shields while using a cheap
and powerful ESP32-S2-Mini board. 

This board can only handle IO voltages up to 3.3V, therefore not every Arduino shield is compatible.

**The features are as follows:**
- ESP32-S2-Mini has more memory, more flash and faster CPU speed compared to Arduino UNO
- no additional components (except the optional LED on GPIO 39)
- simple to assemble (just solder the Mini board and Arduino GPIO headers).
- Digital IO numbering mostly follows AVR UNO pin nmubers
- Extra GPIO pins exposed on the 6-pin side header

**Differences comapred to Arduino UNO**
- 3.3V IO logic only!
- IOREF pin hardwired to 3.3V
- no external AREF, use the internal Analog reference of ESP32-S2
- only 5 Analog pins on the Analog header (A5 is digital only)
- extra analog pins on Digital header pins 1 - 13 (ADC1_0 - ADC2_2)
- no TTL Uart on digital pins 0 and 1 (however the serial input/output is mapped
  to the USB port)

 **Arduino IDE setup**
 
 Install the ESP32 platfrom from Espressif in boards manager. Then select the Board as 'ESP32S2 Dev Module'.
 The rest of the board configuration options is as follows:
![Board image](https://github.com/ole00/bruno-esp32s2mini/raw/master/img/bruno-esp32s2mini-ide.png "bruno-esp32s2mini-ide")

- Ensure "USB CDC On Boot" is Enabled, so that you have the Serial port mapped to USB.
- The sketch upload works automatically, no need to press reset or boot buttons (tested with IDE 2.2.1).
- Note that my CPU frequency is lowered to 40MHz. This might improve compatibility with UNO sketches when they use
  bit-banging technique.