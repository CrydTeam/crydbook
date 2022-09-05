# Configuration.yaml

Beachte hier die `aliase` diese müssen mit den Daten in deiner ICS übereinstimmen.

```
waste_collection_schedule:
  sources:
    - name: ics
      args:
        file: "www/muell.ics"
      customize:
        - type: Restabfall
          alias: Restabfall
          icon: mdi:trash-can
        - type: Papiertonne
          alias: Papiertonne
          icon: mdi:trash-can
        - type: Bioabfall
          alias: Bioabfall
          icon: mdi:trash-can
        - type: Plastikabfall
          alias: Plastikabfall
          icon: mdi:trash-can

  fetch_time: "04:00"
  day_switch_time: "10:00"
```
