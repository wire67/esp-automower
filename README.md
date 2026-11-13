# ESP-Automower (ex. wall-e-esp8266-automower)

Firmware for ESP8266 and ESP32 modules that connects a Gardena / Husqvarna G3 mower to Wi-Fi.

### Features
- Control the mower over its 115200 baud UART, including start, stop, home, and automatic or manual mode commands.
- View mower status, operating mode, cover state, battery measurements, temperature, working hours, and schedules in a mobile-friendly web interface.
- Configure mower timers and working days, and inspect recent logs through the web interface.
- Read status as JSON and send named or raw mower commands through HTTP endpoints.
- Integrate with MQTT, including remote mower commands, telemetry, availability, and automatic Home Assistant entity discovery.
- Update firmware wirelessly using OTA; ESP8266 also supports the web updater.
- Provision Wi-Fi with WiFiManager and use mDNS and NTP time synchronization.
- On ESP32, broadcast an Automower Find My-compatible BLE advertisement.
- Report mower power-outage status and expose firmware and network diagnostics.

### Links
- Forked from: https://gitlab.com/nbrgmn/wall-e-esp8266-automower
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
