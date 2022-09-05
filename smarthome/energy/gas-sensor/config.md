---
description: Diese Config kann mit ESP Home auf den Sensor geflashed werden.
---

# Config

```
esphome:
  name: gaszaehler

esp8266:
  board: nodemcu

# Enable logging
logger:

# Enable Home Assistant API
api:
  password: "kannst du frei vergeben"

ota:
  password: "kannst du frei vergeben"

wifi:
  ssid: "WLANNAME"
  password: "WLANPASSWORT"
  use_address: 192.168.178.51

  # Enable fallback hotspot (captive portal) in case wifi connection fails
  ap:
    ssid: "Gaszaehler Fallback Hotspot"
    password: "VWm7OIPWyPfe"

captive_portal:
    
globals:
  - id: total_pulses
    type: int
    restore_value: false
    initial_value: '1727858'  # hier kann der Gaszählerstand initialisiert werden
binary_sensor:
  - platform: gpio
    id: internal_pulse_counter
    pin:
      number: GPIO5
      mode: INPUT_PULLUP
    name: "Live-Impuls"
    filters:
      - delayed_on: 10ms
    on_press:
      then:
        - lambda: id(total_pulses) += 1;
sensor:
  - platform: template
    name: "Gasverbrauch"
    device_class: gas
    unit_of_measurement: "m³"
    state_class: "total_increasing"
    icon: "mdi:fire"
    accuracy_decimals: 2
    lambda: |-
      return id(total_pulses) * 0.01;
```
