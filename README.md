# wall-e-esp8266-automower

Firmware for an ESP8266 module that connects a Gardena / Husqvarna G3 mower to Wi-Fi.

### Links
- https://www.loxwiki.eu/pages/viewpage.action?pageId=48137811
- https://www.mikrocontroller.net/topic/304526#6198142

### Pinout

The firmware uses a dedicated UART for the mower connection and a relay output.

#### ESP8266 (for example D1 WROOM-02)

| Function | Pin | Note |
| --- | --- | --- |
| Mower RX | D2 / GPIO5 | Mower UART input |
| Mower TX | D1 / GPIO4 | Mower UART output |
| Relay | D3 | Wakeup/reset relay control |

#### ESP32 (for example ESP32 Dev Module)

| Function | Pin | Note |
| --- | --- | --- |
| Mower RX | GPIO16 | Mower UART input |
| Mower TX | GPIO17 | Mower UART output |
| Relay | GPIO4 | Wakeup/reset relay control |

Note: The mower communication runs over a 115200 baud TTL UART. The relay is initialized as a digital output and set to LOW.

### References
- Robomower_V0.8.pdf