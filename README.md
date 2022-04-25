# ATMEGA_UPDI
A template project for ATmega808//1608 processors using PlatformIO and UPDI upload protocol

## Prerequisites
- Install platformIO: https://platformio.org/
- Install `pyupdi.py` with `pip` directly from GitHub:

    `pip install https://github.com/mraardvark/pyupdi/archive/master.zip`

## Connections
Connect the target processor to a TTL Serial port as shown (schematic diagram from mraardvark/pyupdi repo)
<pre>
                        Vcc                     Vcc
                        +-+                     +-+
                         |                       |
 +---------------------+ |                       | +--------------------+
 | Serial port         +-+                       +-+  AVR device        |
 |                     |      +----------+         |                    |
 |                  TX +------+   1k     +---------+ UPDI               |
 |                     |      +----------+    |    |                    |
 |                     |                      |    |                    |
 |                  RX +----------------------+    |                    |
 |                     |                           |                    |
 |                     +--+                     +--+                    |
 +---------------------+  |                     |  +--------------------+
                         +-+                   +-+
                         GND                   GND

</pre>

## Simple Test
To verify the connections between host and target devices:
    `pyupdi -i -d atmega1608 -c /dev/ttyUSB0`
 Which should return something along the lines of:
 
 ```Device info: {'family': 'megaAVR', 'nvm': 'P:0', 'ocd': 'D:1', 'osc': '3', 'device_id': '1E9427', 'device_rev': '0.0'}```
