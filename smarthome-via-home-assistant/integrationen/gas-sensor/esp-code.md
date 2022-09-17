---
description: zum anfügen an die Standard ESP Config
---

# ESP Code



```
globals:
  - id: total_pulses
    type: int
    restore_value: false
    initial_value: '0'  # hier kann der Gaszählerstand initialisiert werden - letze Stelle weglassen
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
    on_release:
      then:
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
