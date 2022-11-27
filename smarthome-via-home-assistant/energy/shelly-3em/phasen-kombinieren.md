---
cover: ../../../.gitbook/assets/energy.png
coverY: 0
---

# Phasen kombinieren

![](<../../../.gitbook/assets/image (8) (1).png>)

ich benutze [dieses Modell](https://amzn.to/3RE9mQd)

## Wie verbinde ich die drei Phasen eines Shellys?

Totaler Verbrauch in W (aktueller Verbrauch für dynamische Anzeige im Dashboard)



<mark style="color:red;">Die nachfolgenden Codes sind in der Template.yaml zu hinterlegen:</mark>

```
- sensor:
    - name: "Total Power"
      unique_id: "Total_Energy"
      device_class: power
      state_class: total
      unit_of_measurement: "W"
      state: >
        {{ 
        states('sensor.hausverbrauch_channel_a_power')| float(0) + 
        states('sensor.hausverbrauch_channel_b_power')| float(0) +
        states('sensor.hausverbrauch_channel_c_power')| float(0) 
        }}
```

Totaler Verbrauch in kWh (für Energy Dashboard)

```
- sensor:
    - name: "Total Energy Use"
      unique_id: "Total_Energy_Use"
      device_class: energy
      state_class: total
      unit_of_measurement: "kWh"
      state: >
        {{ 
        states('sensor.hausverbrauch_channel_a_energy')| float(0) + 
        states('sensor.hausverbrauch_channel_b_energy')| float(0) +
        states('sensor.hausverbrauch_channel_c_energy')| float(0) 
        }}
```

Totale Einspeisung in kWh (für Energie Dashboard)

```
- sensor:
    - name: "Total Energy Returned"
      unique_id: "Total_Energy_Returned"
      device_class: energy
      state_class: total
      unit_of_measurement: "kWh"
      state: >
        {{ 
        states('sensor.hausverbrauch_channel_a_energy_returned')| float(0) + 
        states('sensor.hausverbrauch_channel_b_energy_returned')| float(0) +
        states('sensor.hausverbrauch_channel_c_energy_returned')| float(0) 
        }}
```

### Totale Einspeisung

Totale Einspeisung ( Gesamtstromverbrauch unter 0)

```
- sensor:
    - name: PV Einspeisung
      unique_id: "pv_einspeisung"
      unit_of_measurement: "W"
      device_class: power
      state: "{{ states('sensor.total_power')|float if states('sensor.total_power') | int < 1 else 0 }}"
```

Totale Einspeisung (als Positiv Wert)

```
- sensor:
    - name: PV Einspeisung negiert
      unique_id: "pv_einspeisung_negiert"
      unit_of_measurement: "W"
      device_class: power
      state: "{{ states('sensor.pv_einspeisung')|float * -1 }}"
```
