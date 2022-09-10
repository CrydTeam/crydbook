# Dashboard Karte

```
type: entities
entities:
  - entity: sensor.restmuelltonne_date
    style: |
      :host {
        color: grey;
      }      
    icon: mdi:delete-empty
    show_state: false
    type: custom:multiple-entity-row
    name: Restmüll
    secondary_info: false
    entities:
      - entity: sensor.restmuelltonne_collection
        name: Abholung in
        unit: Tage(n)
      - entity: sensor.restmuelltonne_date
        name: Datum
  - entity: sensor.biotonne_date
    style: |
      :host {
        color: brown;
      }  
    icon: mdi:bio
    show_state: false
    type: custom:multiple-entity-row
    name: Bio Müll
    secondary_info: false
    entities:
      - entity: sensor.biotonne_collection
        name: Abholung in
        unit: Tage(n)
      - entity: sensor.biotonne_date
        name: Datum
  - entity: sensor.papierabfall_date
    style: |
      :host {
        color: turquoise
      }  
    icon: mdi:tree
    show_state: false
    type: custom:multiple-entity-row
    name: Papiertonne
    secondary_info: false
    entities:
      - entity: sensor.papierabfall_collection
        name: Abholung in
        unit: Tage(n)
      - entity: sensor.papierabfall_date
        name: Datum
  - entity: sensor.plastiktonne_date
    style: |
      :host {
        color: yellow
      }  
    icon: mdi:recycle
    show_state: false
    type: custom:multiple-entity-row
    name: Plastik Sack
    secondary_info: false
    entities:
      - entity: sensor.plastikmuelltonne_collection
        name: Abholung in
        unit: Tage(n)
      - entity: sensor.plastiktonne_date
        name: Datum
  - entity: sensor.mybuttoncardsensor
    type: custom:button-card
    layout: icon_name_state2nd
    show_label: true
    label: |
      [[[
       var days_to = entity.state.split("|")[1]
       if (days_to == 0)
       { return "Heute" }
       else if (days_to == 1)
       { return "Morgen" }
       else
       { return "in " + days_to + " Tagen" }
      ]]]
    show_name: true
    name: |
      [[[
        return entity.state.split("|")[0]
      ]]]
    state:
      - color: red
        operator: template
        value: '[[[ return entity.state.split("|")[1] == 0 ]]]'
      - color: orange
        operator: template
        value: '[[[ return entity.state.split("|")[1] == 1 ]]]'
      - value: default
show_header_toggle: true

```
