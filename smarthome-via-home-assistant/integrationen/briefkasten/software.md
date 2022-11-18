# Software

Der Button zum anzeigen bzw. löschen der Briefkastenmeldung:

```
type: custom:mushroom-entity-card
entity: input_boolean.post
tap_action:
  action: call-service
  service: input_boolean.turn_off
  data: {}
  target:
    entity_id: input_boolean.post
  confirmation:
    text: Briefkasten geleert?
secondary_info: last-updated
icon_color: yellow

```

Automation:

```
alias: Benachrichtigung Post
description: ""
trigger:
  - type: opened
    platform: device
    device_id: 0d645b52a4bb04f517b43aa47b037a07
    entity_id: binary_sensor.lumi_lumi_sensor_magnet_aq2_on_off
    domain: binary_sensor
condition:
  - condition: state
    entity_id: input_boolean.post
    state: "off"
action:
  - service: input_boolean.turn_on
    data: {}
    target:
      entity_id: input_boolean.post
  - if:
      - condition: state
        entity_id: group.presence_home
        state: home
    then:
      - service: notify.alexa_media
        data:
          target:
            - media_player.buro
            - media_player.kuche
            - media_player.wohnzimmer
            - media_player.badezimmer
            - media_player.schlafzimmer
          data:
            type: announce
          message: Die Post ist da!
    else:
      - service: notify.notify
        data:
          message: Post ist da!
mode: single

```
