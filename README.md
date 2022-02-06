# ESP-POE-ZB-v1.2
ESP32 POE: ZigBee + BLE gateway

Features:
* ESP32-S (with U.FL connector) used as BLE receiver, main gateway controller,
* Ebyte E72-2G4M20S1E (CC2652p with U.FL connector) as ZigBee coordinator,
* POE 802.3af/802.3at with LAN8720,
* USBC for flashing, based on CH340C (can be used for powering),
* connector for powering 10-57 VDC (abs max 70V - needs to replace capacitor),
* connectors: 3xGPIO (internal pulled up, for SCL, SDA, 1Wire), 3.3V, 5V, GND,
* internal connector: SCL, SDA, 3.3V, GND,
* compatibile with Kradex Z102 enclosure for din rail,
* support for RS485/MODBUD (need to add ISL83485 or similar - note: RS485 disable I2C and 1Wire),
* BUS (input/POE) voltage monitoring.

Pinout:
```
i2c:
  sda: 14
  scl: 13

dallas:
  - pin: 16

uart:
  id: modbus
  tx_pin: 13
  rx_pin: 14
  baud_rate: 115200
  stop_bits: 1

modbus:
  flow_control_pin: 16
  id: modbus1
```
