# ESP Code incl. Sensoren

```
esphome:
  name: bluetoothrepeater

esp32:
  board: esp32dev
  framework:
    type: arduino

# Enable logging
logger:

# Enable Home Assistant API
api:
  encryption:
    key: "Pyj0Ttyg4rMvYCtzcpdAUookNAuAMBWu/EcxvDIqpy0="

ota:
  password: "f1f3301532e4e53b34acc86a6acba692"

wifi:
  ssid: !secret wifi_ssid
  password: !secret wifi_password

  # Enable fallback hotspot (captive portal) in case wifi connection fails
  ap:
    ssid: "Bluetoothrepeater"
    password: "NFSnjxtyYeM1"

captive_portal:

esp32_ble_tracker:

sensor:
  - platform: xiaomi_hhccjcy01
    mac_address: 'C4:7C:8D:6D:37:DC'
    temperature:
      name: "Plant 1 Temperature"
    moisture:
      name: "Plant 1 Moisture"
    illuminance:
      name: "Plant 1 Illuminance"
    conductivity:
      name: "Plant 1 Soil Conductivity"
    battery_level:
      name: "Plant 1 Battery Level"
  - platform: xiaomi_hhccjcy01
    mac_address: 'C4:7C:8D:6D:39:27'
    temperature:
      name: "Plant 2 Temperature"
    moisture:
      name: "Plant 2 Moisture"
    illuminance:
      name: "Plant 2 Illuminance"
    conductivity:
      name: "Plant 2 Soil Conductivity"
    battery_level:
      name: "Plant 2 Battery Level"
```
