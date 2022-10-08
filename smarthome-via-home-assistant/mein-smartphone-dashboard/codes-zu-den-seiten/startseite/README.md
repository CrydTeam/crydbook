# Startseite

```
views:
  - theme: Backend-selected
    title: Home
    type: custom:vertical-layout
    badges: []
    cards:
      - type: custom:mushroom-chips-card
        chips:
          - type: weather
            entity: weather.home
            show_conditions: true
            show_temperature: false
          - type: entity
            entity: >-
              sensor.netatmo_mein_zuhause_weather_station_outdoor_module_temperature
          - type: light
            entity: light.alle_lichter
            tap_action:
              action: navigate
              navigation_path: licht
          - type: template
            icon: mdi:home-lightning-bolt
            icon_color: |-
              {% raw %}
{% if is_state('switch.alle_gerate_ohne_3d_drucker', 'on') %}
                orange
              {% endif %}
            content: |-
              {% if is_state('switch.alle_gerate', 'on') %}
                An
              {% else %}
                Aus
              {% endif %}
            tap_action:
              action: navigate
              navigation_path: gerat
          - type: template
            icon: mdi:window-closed-variant
            icon_color: |-
              {% if is_state('binary_sensor.fenster', 'on') %}
                orange
              {% endif %}
            content: |-
              {% if is_state('binary_sensor.fenster', 'on') %}
                geöffnet
              {% else %}
                geschlossen
              {% endif %}
            tap_action:
              action: navigate
              navigation_path: fenster
          - type: entity
            entity: lock.tur
            tap_action:
              action: toggle
        alignment: center
      - type: horizontal-stack
        cards:
          - type: custom:mushroom-person-card
            entity: person.manuel_fichtner
            icon_type: entity-picture
          - type: custom:mushroom-person-card
            entity: person.selina
            icon_type: entity-picture
      - type: horizontal-stack
        cards:
          - type: custom:mushroom-entity-card
            entity: binary_sensor.garagentor_on_off
            tap_action:
              action: call-service
              service: script.toggle
              data: {}
              target:
                entity_id: script.garage_taster
              confirmation:
                text: Bist du dir sicher?
            icon_color: yellow
          - type: custom:mushroom-entity-card
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
      - type: custom:mushroom-template-card
        primary: Rooms
        secondary: ''
        icon: ''
      - square: false
        columns: 2
        type: grid
        cards:
          - type: custom:mushroom-template-card
            primary: Wohnen
            secondary: >-
              {{
              states('sensor.netatmo_mein_zuhause_weather_station_temperature')
              }} °C / {{
              states('sensor.netatmo_mein_zuhause_weather_station_humidity') }}
              % 
            icon: mdi:sofa
            icon_color: |-
              {% if is_state('light.lichter_wohnzimmer', 'on') %}
                orange
              {% endif %}
            tap_action:
              action: navigate
              navigation_path: wohnen
          - type: custom:mushroom-template-card
            primary: Küche
            secondary: >-
              {{ states('sensor.lumi_lumi_weather_temperature_5') }} °C / {{
              states('sensor.lumi_lumi_weather_humidity_5') }} % 
            icon: mdi:fridge
            icon_color: |-
              {% if is_state('light.lichter_kuche', 'on') %}
                orange
              {% endif %}
            tap_action:
              action: navigate
              navigation_path: kuche
          - type: custom:mushroom-template-card
            primary: Büro
            secondary: >-
              {{ states('sensor.lumi_lumi_weather_temperature_2') }} °C / {{
              states('sensor.lumi_lumi_weather_humidity_2') }} % 
            icon: mdi:desk
            icon_color: |-
              {% if is_state('light.ambiente_pc', 'on') %}
                orange
              {% endif %}
            tap_action:
              action: navigate
              navigation_path: buro
            badge_icon: mdi:electric-switch
            badge_color: |-
              {% if is_state('switch.3d_drucker_on_off', 'on') %}
                red
              {% endif %}
          - type: custom:mushroom-template-card
            primary: Bad
            secondary: >-
              {{ states('sensor.lumi_lumi_weather_temperature_4') }} °C / {{
              states('sensor.lumi_lumi_weather_humidity_4') }} % 
            icon: mdi:shower
            icon_color: >-
              {% if is_state('light.badezimmerlicht_level_light_color_on_off',
              'on') %}
                orange
              {% endif %}
            tap_action:
              action: navigate
              navigation_path: bad
          - type: custom:mushroom-template-card
            primary: Schlafzimmer
            secondary: >-
              {{ states('sensor.lumi_lumi_weather_temperature_3') }} °C / {{
              states('sensor.lumi_lumi_weather_humidity_3') }} % 
            icon: mdi:bed
            icon_color: |-
              {% if is_state('light.schlafzimmerlicht', 'on') %}
                orange
              {% endif %}
            tap_action:
              action: navigate
              navigation_path: schlafzimmer
          - type: custom:mushroom-template-card
            primary: Flur
            icon: mdi:floor-plan
            icon_color: |-
              {% if is_state('light.lichter_flur', 'on') %}
                orange
              {% endif %}
            tap_action:
              action: navigate
              navigation_path: flur
            secondary: >-
              {{ states('sensor.lumi_lumi_weather_temperature') }} °C / {{
              states('sensor.lumi_lumi_weather_humidity') }} % 
          - type: custom:mushroom-template-card
            primary: Keller
            icon: mdi:washing-machine
            icon_color: |-
              {% if is_state('light.waschkuche', 'on') %}
                orange
              {% endif %}
            tap_action:
              action: navigate
              navigation_path: keller
            secondary: >-
              {{ states('sensor.lumi_lumi_weather_temperature_6') }} °C / {{
              states('sensor.lumi_lumi_weather_humidity_6') }} % 
          - type: custom:mushroom-template-card
            primary: Garten
            icon: mdi:tree
            icon_color: ''
            tap_action:
              action: navigate
              navigation_path: garten
            secondary: >-
              {{
              states('sensor.netatmo_mein_zuhause_weather_station_outdoor_module_temperature')
              }} °C / {{
              states('sensor.netatmo_mein_zuhause_weather_station_outdoor_module_humidity')
              }} % 
            fill_container: false
            multiline_secondary: false
      - type: custom:mushroom-template-card
        primary: Status
        secondary: ''
        icon: ''
      - square: false
        columns: 4
        type: grid
        cards:
          - type: custom:mushroom-template-card
            primary: Robots
            icon: mdi:robot
            icon_color: red
            tap_action:
              action: navigate
              navigation_path: robots
            secondary: ''
            layout: vertical
          - type: custom:mushroom-template-card
            primary: PV
            icon: mdi:solar-power-variant
            icon_color: >-
              {% set s = states('sensor.pv_anlage_electrical_measurement')|int
              %}

              {% if s > 300 %}
                green
              {% elif s > 150 %}
                orange
              {% elif s > 1 %}
                red
              {% else %}

              {% endif %}
            tap_action:
              action: navigate
              navigation_path: pv
            secondary: ''
            layout: vertical
          - type: custom:mushroom-template-card
            primary: Energy
            icon: mdi:lightning-bolt
            icon_color: |-
              {% set s = states('sensor.total_power')|int %}
              {% if s < 250 %}
                green
              {% elif s < 500 %}
                orange
              {% elif s > 500 %}
                red
              {% else %}
              {% endif %}
            tap_action:
              action: navigate
              navigation_path: energy
            secondary: ''
            layout: vertical
          - type: custom:mushroom-template-card
            primary: Netzwerk
            icon: mdi:server
            icon_color: >-
              {% if is_state('binary_sensor.fritz_box_7590_cable_link_2', 'on')
              %}
                green
              {% else %}
                red
              {% endif %}
            tap_action:
              action: navigate
              navigation_path: netzwerk
            secondary: ''
            layout: vertical
          - type: custom:mushroom-template-card
            primary: Mercedes
            icon: mdi:car
            icon_color: |-
              {% set s = states('sensor.n_as_690_fuel_level')|int %}
              {% if s > 60 %}
                green
              {% elif s > 30 %}
                orange
              {% elif s > 0 %}
                red
              {% else %}
              {% endif %}
{% endraw %}
            tap_action:
              action: navigate
              navigation_path: car
            secondary: ''
            layout: vertical
          - type: custom:mushroom-template-card
            primary: Smoker
            icon: mdi:grill
            icon_color: blue
            tap_action:
              action: navigate
              navigation_path: smoker
            secondary: ''
            layout: vertical
          - type: custom:mushroom-template-card
            primary: Kalender
            icon: mdi:calendar
            icon_color: blue
            tap_action:
              action: navigate
              navigation_path: kalender
            secondary: ''
            layout: vertical
          - type: custom:mushroom-template-card
            primary: Müll
            icon: mdi:trash-can
            icon_color: blue
            tap_action:
              action: navigate
              navigation_path: mull
            secondary: ''
            layout: vertical
      - type: custom:auto-entities
        card:
          type: entities
          state_color: true
        filter:
          include:
            - attributes:
                device_class: battery
              state: <30
            - type: ''
          exclude: []
        show_empty: false
```
