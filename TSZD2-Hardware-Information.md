This project came from [Flexible Opensource Firmware](https://opensourceebikefirmware.bitbucket.io/FLEXIBLE_OPENSOURCE_FIRMWARE.html), and there is more information there, especially [Hardware information and manuals](https://opensourceebikefirmware.bitbucket.io/development_tsdz2/)

[LCD3 - TSZD2 Wiring](https://github.com/OpenSource-EBike-firmware/TSDZ2_wiki/wiki/Wire-KT-LCD3-to-TSDZ2)

[Offical Tongsheng Protocol](https://endless-sphere.com/forums/download/file.php?id=239100) and reputedly better [Hurzhurz version](https://github.com/hurzhurz/tsdz2/blob/master/serial-communication.md#motor-control-flags)

# Display Units

Original TS displays VLCD5 and XH-18 use otp haier micros, and can't be changed. 

[More display info](https://opensourceebikefirmware.bitbucket.io/development/Motor_controllers--BMSBattery_S_series--LCD_control_panel.html)

KT-LCD3 uses STM8S105C6T6 that has 32kbytes of flash memory, which should be plenty.
The only other IC on the board is the LCD controller [Holtek HT1622](http://www.holtek.com/productdetail/-/vg/ht1622) that has datasheet in English language, there are even [OpenSource Arduino firmware for it](https://github.com/MartyMacGyver/LCD_HT1622_16SegLcd). 

Appears to be [variants with a different display driver](https://endless-sphere.com/forums/download/file.php?id=234155&mode=view) (SHT32E22) but it looks like its pin compatible for the connected pins.

- [KT-LCD3 LCD Pattern](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTTM-CTAZAUMd8RtW5SWPnMefDgj7QYZbeXzm2miu3nnYPnQ5ZL)
- [KT-LCD5 LCD Pattern](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcThFBCCEStyp3k5i-E7BqNa28befkmFGdpKD2JHCAMJ5jXkLnptWw)
- [KT-LCD6 LCD Pattern](https://elektrolurchbike.de/osCommerce2.3.1Deutsch/catalog/images/schema%20lcd6.jpg)

[KT-LCD5B](https://opensourceebikefirmware.bitbucket.io/development/images/13-2.png) also appears to use the same chips, less voltage and power numbers. How compatible is it with LCD3? 

The first part of the Schematic is done (the interesting bits LOL)
 [LCD3_display_V0_1.pdf](http://52.25.253.50/forums/download/file.php?id=234642&sid=dfac13d38edaa1476f4da58a6ea999f7)

few intersting things i see:

PA2 needs to be logic HIGH to keep the LCD on. this works like a keep alive. write a low and the LDO loses power and turns off (i tested this behaviour)

with PE3 you can short part of the resistors before the LDO. i think this is to accomodate different input voltages.

STM8 reads the battery voltage on pin PE7. The current value is sent by the controller over UART. 

[I burn my KT LCD3, I connect 48V version to 14s battery (about 58V)](https://endless-sphere.com/forums/viewtopic.php?f=2&t=94070&start=75#p1395703)

## KT-LCD3 Connectors



[Connector closeup](https://sondorsforum.com/applications/core/interface/imageproxy/imageproxy.php?img=https%3A%2F%2Fi.imgur.com%2FGqfwM0S.jpg&key=1203f163b099843d28eb7d621793818bafcc3cbc1c177a2dd9ee66a2afc4ae07)

What kind are these? Where to buy? 

---

## TSZD2 and VLCD5 Connectors

6 pin controller (without throttle wire):
- green | P+ | battery voltage!!
- black | GND | ground
- white | Vin | ground when LCD disabled and P+ (battery voltage) when LCD is enabled
- brown | UART TX motor controller |
- orange | UART RX motor controller |
- purple | brake | this signal is active low, meaning that when brakes are not active, this wire has 5V and with brakes active this wire has 0 volts.

8 pin controller (with throttle wire):
- blue | P+ | battery voltage
- black | GND | ground
- red | Vin | ground when LCD disabled and P+ (battery voltage) when LCD is enabled
- brown | UART TX motor controller |
- yellow | UART RX motor controller |
- green | brake | this signal is active low, meaning that when brakes are not active, this wire has 5V and with brakes active this wire has 0 volts. Wired with the 5V wire and black GND wire for 3 pin throttle
- white | 5V | 
- orange | throttle | wired with the 5V wire and black ground wire for 3 pin throttle

