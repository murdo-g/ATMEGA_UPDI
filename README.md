# ATMEGA_UPDI
A template project for ATmega808//1608 processors using PlatformIO and UPDI upload protocol

## Prerequisites
- Install platformIO: https://platformio.org/
- Install `pyupdi.py` with `pip` directly from GitHub:

    `pip install https://github.com/mraardvark/pyupdi/archive/master.zip`

## Connections
Connect the target processor to a TTL Serial port as shown
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
