# ESP-DMX-WiFi

Art-Net to DMX gateway. It supports RDM and sACN (E1.31) too.

![](images/Assembled.png)

Strongly based on amazing [LXDMXWiFi_Library](https://github.com/claudeheintz/LXDMXWiFi_Library) example [ESP-DMX](https://github.com/claudeheintz/LXDMXWiFi_Library/tree/master/examples/ESP-DMX)).

Configuration utility for macOS and Windows is [here](https://github.com/claudeheintz/LXDMXWiFi_Library/tree/master/examples/configuration%20utility)


## Bill of materials

- ESP01S board
- RS-485 transceiver like SN75176 or MAX485 or equivalent
- Male XLR panel mount connector
- 3x 5K Ohn 1/4 watt resistor
- 2x push buttons

## Schematic

```                       
+------------------------------------------+
| |                                        |
| |                         RX0 +  + 3.3V  |
| +---+  |                                 |
| +---+  |   +--------+   GPIO0 +  + RST   |
| +---+  |   | ESP01S |                    |
| +---+  |   +--------+   GPIO2 +  + CH_PD |
| +---+  |                                 |
| +---+  |                  GND +  + TX0   |
| +------+                                 |
+------------------------------------------+
 
          3.3V 
           + 
           | 
           \      RESET
        5K /      Button
           \        |
           |      --+-- 
RST   -----+-----+     +----- GND


          3.3V 
           + 
           | 
           \      PROGRAM
        5K /      Button
           \        |
           |      --+-- 
GPIO0 -----+-----+     +----- GND


          3.3V 
           + 
           | 
           \
        5K /
           \ 
           |
CH_PD -----+


                     +5V
                      |
        +-------------+-----------+               
        |                         |
        |     +---------------+   |
        |   --| R         VCC |---+       DMX OUT
        |     |               |
        |   --| RE/         B |---------- Data - (XLR pin 2)
        |     |    SN75176    |
        +-----| DE          A |---------- Data + (XLR pin 3)
              |               |
GPIO2 --------| D         GND |---+------ Ground (XLR pin 1)
              +---------------+   |
                                  |
                                 GND
```

## Images

![](images/Open%20from%20USB%20side.png)
![](images/Open%20from%20DMX%20side.png)


