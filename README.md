# ESP-POE-ZB-v1.2
ESP32 POE: ZigBee + BLE gateway

Features:
* ESPHome compatible,
* ESP32-S (with U.FL connector) used as BLE receiver, main gateway controller,
* Ebyte E72-2G4M20S1E (CC2652p with U.FL connector) as ZigBee coordinator,
* POE 802.3af/802.3at (36-57 VDC) with LAN8720,
* passive POE 12-57V (experimental, need to solder jumper on PCB),
* USBC for flashing, based on CH340C (can be used for powering),
* power connector: 10-57 VDC (abs max 70V - needs to replace capacitor),
* external connectors: 3xGPIO (internal pulled up, for SCL, SDA, 1Wire), 3.3V, 5V, GND,
* internal connectors: SCL, SDA, 3.3V, GND (SCL and SDA shared with external connector; more gpio available without zigbee module),
* compatibile with Kradex Z102 enclosure for din rail,
* support for RS485/MODBUS (need to add ISL83485 or similar - note: RS485 disable I2C and 1Wire),
* BUS (input/POE) voltage monitoring,
* LEDs: power (green) and status (amber).


### DO NOT POWER ON MODULE WITHOUT ANTENNAS

Example ESPHome yaml file: https://github.com/ficueu/ESP-POE-ZB-v1.2/blob/main/esp-poe-test1.yaml

Enclosure STL files: https://github.com/ficueu/ESP-POE-ZB-v1.2/tree/main/enclosure

Pinout:
```
i2c:
  sda: 14
  scl: 13

dallas:
  - pin: 16

uart:
  id: modbus
  tx_pin: 14
  rx_pin: 13
  baud_rate: 115200
  stop_bits: 1

modbus:
  flow_control_pin: 16
  id: modbus1
```

ZigBee2MQTT config:

```
serial:
  port: tcp://YOUR-IP:1234
```

![alt text](https://github.com/ficueu/ESP-POE-ZB-v1.2/blob/main/images/board1.2.png)