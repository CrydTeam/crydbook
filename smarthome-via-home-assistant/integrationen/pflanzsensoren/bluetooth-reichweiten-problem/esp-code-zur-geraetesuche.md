---
description: diesen Code nimmst du um alle Bluetooth Geräte in Reichweite zu finden.
---

# ESP Code zur Gerätesuche



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
```

Als Ergebnis solltet ihr dann folgendes im Log finden:

<figure><img src="../../../../.gitbook/assets/image (17).png" alt=""><figcaption></figcaption></figure>

Diese Mac Adresse benötigt ihr jetzt um den Sensor auf der nächsten Seite einzubinden.
