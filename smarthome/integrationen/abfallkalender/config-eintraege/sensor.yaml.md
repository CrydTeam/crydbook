# Sensor.yaml

(ich hoffe du hast dir diese erstellt ansonsten einfach erstellen und mit \`\`\`sensor: !include sensor.yaml\`\`\`\` in der configuration.yaml einbinden)

```
########################## Müllabfuhr ###########################

- platform: waste_collection_schedule
  name: Papierabfall_date
  value_template: '{{value.date.strftime("%d.%m.%Y")}}'
  types:
    - Papiertonne
- platform: waste_collection_schedule
  name: Papierabfall_collection
  value_template: "{{value.daysTo}}"
  types:
    - Papiertonne

- platform: waste_collection_schedule
  name: Restmuelltonne_date
  value_template: '{{value.date.strftime("%d.%m.%Y")}}'
  types:
    - Restabfall
- platform: waste_collection_schedule
  name: Restmuelltonne_collection
  value_template: "{{value.daysTo}}"
  types:
    - Restabfall

- platform: waste_collection_schedule
  name: Plastiktonne_date
  value_template: '{{value.date.strftime("%d.%m.%Y")}}'
  types:
    - Plastikabfall
- platform: waste_collection_schedule
  name: Plastikmuelltonne_collection
  value_template: "{{value.daysTo}}"
  types:
    - Plastikabfall

- platform: waste_collection_schedule
  name: Biotonne_date
  value_template: '{{value.date.strftime("%d.%m.%Y")}}'
  types:
    - Bioabfall
- platform: waste_collection_schedule
  name: Biotonne_collection
  value_template: "{{value.daysTo}}"
  types:
    - Bioabfall

- platform: waste_collection_schedule
  name: next_waste_collection_daysto
  details_format: upcoming
  value_template: '{{value.types|join(", ")}} in {{value.daysTo}} Tagen'

  #button-card#
- platform: waste_collection_schedule
  name: MyButtonCardSensor
  value_template: '{{value.types|join(", ")}}|{{value.daysTo}}|{{value.date.strftime("%d.%m.%Y")}}|{{value.date.strftime("%a")}}'
```
