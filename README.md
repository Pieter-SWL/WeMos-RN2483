ESP8266 WeMos Shield for microchip LORAWAN RN2483 or RN2903
===========================================================

<img src="https://raw.githubusercontent.com/hallard/WeMos-RN2483/master/pictures/RN2483-Stacked.jpg" alt="WeMos With RN2483"  width="50%" height="50%"> 

This shield is used to hold [RN2483][4] Software with WeMos ESP8266 boards it has just few minimal features. 
- I2C Pullups placement
- Classic I2C 128x64 OLED connector
- Placement for Microchip LoraWan [RN2483][4] or [RN2903][4] module
- Placement for choosing single Wire, SMA or u-FL Antenna type for both 433MHz and 868MHz output
- Solder pad choosing 2 RX/TX available on ESP8266 (GPIO1/GPIO3 or GPIO13/GPIO12 to avoid conflict with onboard USB/Serial of WeMos)
- WS2812B Type LED for visual indication
- Custom switch on GPIO14

You can find more information on WeMos on their [site][1], it's really well documented. There is also a nice blog post on Microchip module made by disk91 [here][5]
I now use WeMos boards instead of NodeMCU's one because they're just smaller, features remains the same, but I also suspect WeMos regulator far better quality than the one used on NodeMCU that are just fake of originals AMS117 3V3.

**Boards arrived from OSHPark, I tested them, worked out of the box but I made new revision cand corrected some mistakes**
V1.1 contain the following changes:
- Error with RX/TX swapped on ESP8266, they are GPIO15/GPIO13 nor GPIO12/GPIO13 (so with V1.0 you can use SoftSerial or Native RX/TX of ESP but not in swapped mode)
- I made larger pad for Microchip module, even if I have strong experience in soldering in SMD, it was a pain to do them see picture below, I suspected board/solder. Ok made some new ones, think now I've got the technique ;-)
- Switch moved from GPIO14 to GPIO2, so I removed pullup because WeMos already have one on GPIO2
- Removed GPIO0 and GPIO11 from RN2483 to avoid as much as possible closer PAD

**Waiting for V1.1 Boards from OSHPark, I did not fully tested them yet, I will update ASAP. Use at your own risks**

Detailed Description
====================

Look at the schematics for more informations.

### Firmware

You can WiFi to Serial with a firmware like [WebSocketToSerial][6] I made for this kind of functions.

### Action
<img src="https://raw.githubusercontent.com/hallard/WeMos-RN2483/master/pictures/web-terminal.jpg" alt="Web Console">&nbsp;

### Schematic
![schematic](https://raw.githubusercontent.com/hallard/WeMos-RN2483/master/WeMos-RN2483-sch.png)  

### Boards 
<img src="https://raw.githubusercontent.com/hallard/WeMos-RN2483/master/WeMos-RN2483-top.png" alt="Top" width="40%" height="40%">&nbsp;
<img src="https://raw.githubusercontent.com/hallard/WeMos-RN2483/master/WeMos-RN2483-bot.png" alt="Bottom" width="40%" height="40%">&nbsp; 

You can order the PCB of this board at [OSHPARK][3]

### Assembled boards (V1.0)

<img src="https://raw.githubusercontent.com/hallard/WeMos-RN2483/master/pictures/WeMos-RN2483-top.jpg" alt="Top">&nbsp;
<img src="https://raw.githubusercontent.com/hallard/WeMos-RN2483/master/pictures/WeMos-RN2483-bot.jpg" alt="Bottom">&nbsp; 
<img src="https://raw.githubusercontent.com/hallard/WeMos-RN2483/master/pictures/WeMos-RN2483-mod.jpg" alt="Bottom With RN2483">&nbsp; 

##License

You can do whatever you like with this design.

##Misc
See news and other projects on my [blog][2] 
 
[1]: http://www.wemos.cc/Products/d1_mini.html
[2]: https://hallard.me
[3]: https://oshpark.com/shared_projects/G3MI8Wk2
[4]: http://www.microchip.com/wwwproducts/Devices.aspx?product=RN2483
[5]: https://www.disk91.com/2015/technology/networks/first-step-in-lora-land-microchip-rn2483-test/
[6]: https://github.com/hallard/WebSocketToSerial
[7]: http://www.microchip.com/wwwproducts/Devices.aspx?product=RN2903
