# ESP12_DEV
A development board for the ESP12 and ESP12E WiFi modules. Featuring some useful sensors and required peripherals to make it work.

## Rev 00

![ESP12_DEV_00](https://raw.githubusercontent.com/phyx-be/ESP12_DEV/master/ESP12_DEV_00/3D_VIEW.png)

Initial board version with 3.3V LDO and 5V LDO. 
#### Known issues : 
- TXB0106 symbol is wrong resulting in a short circuit
- 3V3 LDO will get hot when board is powered with 12V

## Rev 01

![ESP12_DEV_01](https://raw.githubusercontent.com/phyx-be/ESP12_DEV/master/ESP12_DEV_01/3D_VIEW.png)

- Replaced the 3.3V LDO with a [TPS562209](http://www.ti.com/product/tps562209) based switching power supply to reduce power dissipation.
- Added more capacitors to increase stability

## Features

- 3V3 level FTDI-compatible UART pin header
- push buttons for reset and boot
- 7 - 12VDC power input
- 5V power input possible when bypassing internal 5V LDO with 0 Ohm resistor or ferrite bead.
- 6 bidirectional 5V I/O pins
- Microphone
- Temperature and humidity sensor


Component | Description | Notes | IO pin
----------|-------------|-------|--------
[TXB0106](http://www.ti.com/product/txb0106) | 6 bit level translator | Interfacing with 5V I/O | 4,9,10,12,13,14
[DS18B20](http://www.maximintegrated.com/en/products/analog/sensors-and-sensor-interface/DS18B20.html) | 1-Wire temperature sensor | Shares pin with DHT11 | 5
[DHT11](http://www.aosong.com/en/products/details.asp?id=109) | Temperature and humidity sensor | Shares pin with DS18B20 | 5
LED | General purpose LED | | 16
[EKMC1601113](http://na.industrial.panasonic.com/products/sensors/sensors-automotive-industrial-applications/pir-motion-sensor-papirs/series/vz-series/2481) | Digital motion detection | Shares I/O pin with TXB0106 | 4
MIC | Electret Microphone with amplifier circuit | ADC has max input of 1V | ADC
