View this project on [CADLAB.io](https://cadlab.io/project/2519). 

# STM32 Debug Adapter Board

Adapter for various SWD programmers for STM32. 

<img width="600" src="https://github.com/fronders/fronders.github.io/raw/master/stm32-debug-adapter/stlink+adapter.jpg" label="STM32 debug adapter board rev.A with Chinese ST-Link V2 clone">
<br />
<img width="600" src="https://github.com/fronders/fronders.github.io/raw/master/stm32-debug-adapter/stm32%20debug%20adapter%20rev.A.jpg" label="STM32 debug adapter board rev.A top and bottom">

This repo contains:
- Autodesk Eagle CAD v9 project
- PDF schematic & board layout
- Gerber files (in PCBWay-compatible format: RS-274X + Excellon)

What's here in README:
- [Supported STM32 programmers](#Supported-STM32-programmers)
- [Interfaces pinout](#Interfaces-pinout)
	- [Original ST-Link V2 by STMicroelectronics](#Original-ST-Link-V2-by-STMicroelectronics)
	- [J-Link by SEGGER](#J-Link-by-SEGGER)
	- [Chinese ST-Link V2 dongle](#Chinese-ST-Link-V2-dongle)
	- [Chinese MX-Link dongle](#Chinese-MX-Link-dongle)
	- [Nucleo-32 original ST-Link V2-1 by STMicroelectronics](#Nucleo-32-original-ST-Link-V2-1-by-STMicroelectronics)
	- [Nucleo-64 original ST-Link V2-1 by STMicroelectronics](#Nucleo-64-original-ST-Link-V2-1-by-STMicroelectronics)
	- [Nucleo-144 original ST-Link V2-1 by STMicroelectronics](#Nucleo-144-original-ST-Link-V2-1-by-STMicroelectronics)
	- [Blue Pill board (STM32F103C8T6)](#Blue-Pill-board-(STM32F103C8T6))
	- [Black Pill board (STM32F103C8T6)](#Black-Pill-board-(STM32F103C8T6))
	- [Tag-Connect 6 Pin Cable (TC2030-IDC)](#Tag-Connect-6-Pin-Cable-(TC2030-IDC))
- [Rev. B board info](#Rev.-B-board-info-(latest))
- [Rev. A board info](#Rev.-A-board-info)
- [Original board info](#Original-board-info)

<hr />

## Supported STM32 programmers

- Original ST-Link V2 by STMicroelectronics
- Nucleo original ST-Link V2-1 by STMicroelectronics
- Chinese ST-Link V2 clones (2 versions: ST-Link & MX-Link - different pinouts)
- J-Link by SEGGER

<hr />

## Interfaces pinout

### Original ST-Link V2 by STMicroelectronics

<img width="350" src="https://github.com/fronders/fronders.github.io/raw/master/stm32-debug-adapter/original%20stlink.jpg" label="Original ST-Link V2">

STM32 connector pinout:

| Name | Pin | Pin | Name |
| ---: | :---: | :---: | :--- |
| VDD_TRGT | 1 | 2 | VDD_TRGT |
| NC | 3 | 4 | GND |
| NC | 5 | 6 | GND |
| SWDIO | 7 | 8 | GND |
| SWCLK | 9 | 10 | GND |
| NC | 11 | 12 | GND |
| SWO | 13 | 14 | GND |
| NRST | 15 | 16 | GND |
| NC | 17 | 18 | GND |
| 3.3V | 19 | 20 | GND | 

### J-Link by SEGGER

<img width="350" src="https://github.com/fronders/fronders.github.io/raw/master/stm32-debug-adapter/jlink.jpg" label="J-Link">

Target connector pinout:

| Name | Pin | Pin | Name |
| ---: | :---: | :---: | :--- |
| 3.3V | 1 | 2 | NC |
| NC | 3 | 4 | GND |
| NC | 5 | 6 | GND |
| SWDIO | 7 | 8 | GND |
| SWCLK | 9 | 10 | GND |
| NC | 11 | 12 | GND |
| SWO | 13 | 14 | GND |
| NRST | 15 | 16 | GND |
| NC | 17 | 18 | GND |
| 5V | 19 | 20 | GND

### Chinese ST-Link V2 dongle

<img width="350" src="https://github.com/fronders/fronders.github.io/raw/master/stm32-debug-adapter/chinese%20stlink.jpg" label="Chinese ST-Link V2 dongle">

SWD connector pinout:

| Name | Pin | Pin | Name |
| ---: | :---: | :---: | :--- |
| RST\* | 1 | 2 | SWDIO |
| GND | 3 | 4 | GND |
| SWO\* | 5 | 6 | SWCLK |
| 3.3V | 7 | 8 | 3.3V |
| 5V\*\* | 9 | 10 | 5V\*\*

\* - not connected on the device, need to modify ST-Link: cut STM8's tracks for nRST & SWIM signals to become instead STM32's nRST (STM32 pin 18) & SWO (STM32 pin 31) signals

\*\* - not connected on adapter board

### Chinese MX-Link dongle

<img width="350" src="https://github.com/fronders/fronders.github.io/raw/master/stm32-debug-adapter/chinese%20mxlink.jpg" label="Chinese MX-Link dongle">

SWD connector pinout:

| Name | Pin | Pin | Name |
| ---: | :---: | :---: | :--- |
| RST\* | 1 | 2 | SWCLK |
| SWO\* | 3 | 4 | SWDIO |
| GND | 5 | 6 | GND |
| 3.3V | 7 | 8 | 3.3V |
| 5V\*\* | 9 | 10 | 5V\*\*

\* - not connected on the device, need to modify MX-Link: cut STM8's tracks for nRST & SWIM signals to become instead STM32's nRST (STM32 pin 18) & SWO (STM32 pin 31) signals

\*\* - not connected on adapter

### Nucleo-32 original ST-Link V2-1 by STMicroelectronics

<img width="350" src="https://github.com/fronders/fronders.github.io/raw/master/stm32-debug-adapter/nucleo32.jpg" label="Nucleo-32 original ST-Link V2-1">

CN2 connector pinout:

| Name | Pin | Pin | Name |
| ---: | :---: | :---: | :--- |
| - | - | 5 | NC |
| 3.3V | 4 | 3 | SWCLK |
| GND | 2 | 1 | SWDIO

### Nucleo-64 original ST-Link V2-1 by STMicroelectronics

<img width="350" src="https://github.com/fronders/fronders.github.io/raw/master/stm32-debug-adapter/nucleo64.jpg" label="Nucleo-64 original ST-Link V2-1">

CN4 connector pinout:

| Pin | Name |
| ---: | :--- |
| 1 | VDD_TRGT |
| 2 | SWCLK |
| 3 | GND |
| 4 | SWDIO |
| 5 | NRST |
| 6 | SWO

### Nucleo-144 original ST-Link V2-1 by STMicroelectronics

<img width="350" src="https://github.com/fronders/fronders.github.io/raw/master/stm32-debug-adapter/nucleo144.jpg" label="Nucleo-144 original ST-Link V2-1">

CN6 connector pinout:

| Pin | Name |
| ---: | :--- |
| 1 | VDD_TRGT |
| 2 | SWCLK |
| 3 | GND |
| 4 | SWDIO |
| 5 | NRST |
| 6 | SWO

### Blue Pill board (STM32F103C8T6)

<img width="350" src="https://github.com/fronders/fronders.github.io/raw/master/stm32-debug-adapter/bluepill.jpg" label="Blue Pill board">

Programming connector pinout:

| Pin | Name |
| ---: | :--- |
| 1 | GND |
| 2 | SWCLK |
| 3 | SWDIO |
| 4 | 3.3V

### Black Pill board (STM32F103C8T6)

<img width="350" src="https://github.com/fronders/fronders.github.io/raw/master/stm32-debug-adapter/blackpill.jpg" label="Black Pill board">

Programming connector pinout:

| Pin | Name |
| ---: | :--- |
| 1 | GND |
| 2 | SWCLK |
| 3 | SWDIO |
| 4 | 3.3V

### Tag-Connect 6 Pin Cable (TC2030-IDC)

<img width="350" src="https://github.com/fronders/fronders.github.io/raw/master/stm32-debug-adapter/tc2030-idc-cable.jpg" label="Tag-Connect cable">
<br />
<img height="145" src="https://github.com/fronders/fronders.github.io/raw/master/stm32-debug-adapter/tc2030-idc.jpg" label="Tag-Connect socket">
<img height="145" src="https://github.com/fronders/fronders.github.io/raw/master/stm32-debug-adapter/arm20-ctx.jpg" label="Tag-Connect adapter">

IDC-6 connector pinout:

| Name | Pin | Pin | Name |
| ---: | :---: | :---: | :--- |
| 3.3V | 1 | 2 | SWDIO |
| NRST | 3 | 4 | SWCLK |
| GND | 5 | 6 | SWO

<hr />

## Rev. B board info (latest)

PDF schematic & board:
- [Rev. B single file](pdf/rev.B/stm32%20debug%20adapter%20rev.B.pdf)
- [Rev. B schematic](pdf/rev.B/stm32%20debug%20adapter%20rev.B%20sch.pdf)
- [Rev. B board](pdf/rev.B/stm32%20debug%20adapter%20rev.B%20brd.pdf)

Solder jumper can be used with Original ST-Link to connect IDC-20 pin 19 VDD (3.3V) to rest of 3.3V (pins 1-2). **Jumper should remain open for use with J-Link, it has 3.3V output on pin 1, while pin 19 has 5V, might damage your board!**

Changes:
- Changed SWD pin header to match Nucleo ST-Link V2-1 pinout
- Fixed Blue Pill / Black Pill board (STM32F103C8T6) connector to be non-mirrored
- Added a solder jumper (NO) between pin 19 and pins 1-2 for Original ST-Link V2 to provide 3.3V power
- Added power indicator LED

Supported interfaces:
- Chinese ST-Link V2 dongle
- Chinese MX-Link dongle
- J-Link / Original ST-Link V2
- Tag-Connect (TC2030-IDC)
- Nucleo original ST-Link V2-1
- Blue Pill / Black Pill board

Known issues:
- none

<hr />

## Rev. A board info

PDF schematic & board:
- [Rev. A single file](pdf/rev.A/stm32%20debug%20adapter%20rev.A.pdf)
- [Rev. A schematic](pdf/rev.A/stm32%20debug%20adapter%20rev.A%20sch.pdf)
- [Rev. A board](pdf/rev.A/stm32%20debug%20adapter%20rev.A%20brd.pdf)

Changes:
- Added Blue Pill / Black Pill board (STM32F103C8T6) connector

Supported interfaces:
- Chinese ST-Link V2 dongle
- Chinese MX-Link dongle
- J-Link / Original ST-Link V2
- Tag-Connect (TC2030-IDC)
- SWD pin header
- Blue Pill / Black Pill board

Known issues:
- Blue Pill header mirrored, **need to plug in board upside down (chip facing down)**
- Original ST-Link V2 does not provide 3.3V on pins 1-2 (it is VDD_Target input instead), need to connect pin 19 to pins 1-2 on IDC-20 connector with external wire. J-Link works okay, as pin 1 has 3.3V output.

<hr />

## Original board info

PDF schematic & board:
- [Original schematic](pdf/original/stm32%20debug%20adapter%20sch.pdf)

Supported interfaces:
- Chinese ST-Link V2 dongle
- Chinese MX-Link dongle
- J-Link / Original ST-Link V2
- Tag-Connect (TC2030-IDC)
- SWD pin header

Known issues:
- Original ST-Link V2 does not provide 3.3V on pins 1-2 (it is VDD_Target input instead), need to connect pin 19 to pins 1-2 on IDC-20 connector with external wire. J-Link works okay, as pin 1 has 3.3V output.