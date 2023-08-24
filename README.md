# ESP-DMX-WiFi

Art-Net to DMX gateway. It supports RDM and sACN (E1.31) too.

![](images/Assembled.png)

Strongly based on amazing [LXDMXWiFi_Library](https://github.com/claudeheintz/LXDMXWiFi_Library) example [ESP-DMX](https://github.com/claudeheintz/LXDMXWiFi_Library/tree/master/examples/ESP-DMX)).

Configuration utility for macOS and Windows is [here](https://github.com/claudeheintz/LXDMXWiFi_Library/tree/master/examples/configuration%20utility)

Changes from original source are:
```

....

#define USE_REMOTE_CONFIG      0    // uncommented line for enable the configuration utility
```

## Bill of materials

- ESP01S board
- RS-485 transceiver like SN75176 or MAX485 or equivalent
- Male XLR panel mount connector
- 2x M3 x 8 mm bolts
- 2x M3 nuts

## Schematic

```                       
                         +---------------+
                    -----| R         VCC |---------- +5V
                         |               |
                    +----| RE/         B |---------- Data - (XLR pin 2)
                    |    |    SN75176    |
GPIO04      --------+----| DE          A |---------- Data + (XLR pin 3)
                         |               |
TX2/GPIO17  -------------| D         GND |---+------ Ground (XLR pin 1)
                         +---------------+   |
                                             |
                                            GND
```

## Images

![](images/Open%20from%20USB%20side.png)
![](images/Open%20from%20DMX%20side.png)


