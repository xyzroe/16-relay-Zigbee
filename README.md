[![Stand With Ukraine](https://raw.githubusercontent.com/vshymanskyy/StandWithUkraine/main/banner-direct-single.svg)](https://stand-with-ukraine.pp.ua)

# 16-relay-Zigbee
Zigbee sub board to 16 relays board using CC2652, with 4 isolated digital inputs, 4 direct pins, DS18B20 on board and CH340 for flashing using USB.
![Main view](https://i.imgur.com/ORnDNKh.jpg)



Front | Back
:-:|:-:
![PCB front view](images/front.png)  | ![PCB back view](images/back.png)
![External sensor](https://i.imgur.com/LFHT67z.jpg)  | ![Back side](https://i.imgur.com/41dWDfy.jpg)

### Schematic
![Schematic](hardware/Schematic.png)


## Jumpers
Due to the fact that the Zigby module has only 16 free pins, you have to give up some relays if you need to use input pins or sensors.

**Relays that always connected:**  
D7 - Relay 1  
...  
D11 - Relay 5   
D14 - Relay 6   
D18 - Relay 7    
D19 - Relay 8    

**Relays with jumpers:**  
D20 - Relay 9  
...  
D27 - Relay 16  

![Jumpers description](images/jumpers.png)  
**RED** - isolated digital input on X1,X2  
**GREEN** - relay boards on X0  
**YELLOW** - direct IO on X3, X4  

*JP - connect DS18B20 to CC2652 TDI_D17 (may lead to the inability to flash using DEBUG)*  
*LED always connected to TDO_D16*  
*Button always connected to D15 (BSL or SBL pin)*  

## Inputs
**SOLDER ONLY ONE COLOR**  
![Inputs description](images/inputs.png)  
**RED** - HIGH VOLTAGE control (5-300 AC/DC)   
**Electrical Hazard Risk**    

**YELLOW** - low voltage control (GND)


## Firmware - PTVO
In most cases, you will need the premium version. but it also works on the free version.
Below is one of the configuration options.
![PTVO config](images/ptvo.png)


## Flashing
CC2652 comes with firmware with Serial bootloader (SBL) activated, so you don't need J-Link.   
I prefer to use [ZigStarGW-MT](https://github.com/xyzroe/ZigStarGW-MT), but you can also use cc2538_bsl.py or Flash Programmer 2.  

***Don't forget to activate SBL while making your firmware, otherwise you will need J-Link programmer to reactivate it***

## 3.3V relay board mod
Some revisions of 16-channel relay boards cannot control using 3.3V voltage, because, built-in optocouplers are powered by 5V.
Such boards need to be slightly redone - to separate the power supply of optocouplers from 5V and apply 3.3V to them.

An example of where you can take 3.3V is in the photo below (AMS1117).
![Relay board 3.3v mod](https://i.imgur.com/AWW3jOZ.jpg)

### Binding
The firmware supports direct binding on input and output endpoints.


### Files to reproduce
* [Gerbers and BOM](https://github.com/xyzroe/16-relay-Zigbee/hardware)
* [Firmware - PTVO](https://ptvo.info)


### Like ♥️?
[!["Buy Me A Coffee"](https://www.buymeacoffee.com/assets/img/custom_images/orange_img.png)](https://www.buymeacoffee.com/xyzroe)

[![Made in Ukraine](https://img.shields.io/badge/made_in-ukraine-ffd700.svg?labelColor=0057b7)](https://stand-with-ukraine.pp.ua)
