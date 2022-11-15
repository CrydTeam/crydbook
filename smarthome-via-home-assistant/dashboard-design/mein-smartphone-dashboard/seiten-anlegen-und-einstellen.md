# Seiten anlegen und einstellen

<figure><img src="../../../.gitbook/assets/image (2) (1) (2).png" alt=""><figcaption><p>bei der Seitenerstellung bitte die YAML anpassen </p></figcaption></figure>

```
theme: Backend-selected
title: Büro
path: buro
type: custom:vertical-layout
subview: false
badges: []
```

Jetzt geht es an die Grundstruktur des ersten Raumes hier habe ich meist folgende Config:

```
type: vertical-stack
cards:
  - type: custom:mushroom-chips-card
    chips:
      - type: template
        icon: mdi:arrow-left-bold
        picture: ''
        content: Home
        tap_action:
          action: navigate
          navigation_path: /lovelace-yotube/smartphonehome
      - type: entity
        entity: sensor.TEMPERATUR
      - type: entity
        entity: sensor.LUFTFEUCHTIGKEIT
  - type: custom:mushroom-template-card
    primary: Lichter
    secondary: ''
    icon: ''
  - type: vertical-stack
    cards: []
  - type: custom:mushroom-template-card
    primary: Geräte
    secondary: ''
    icon: ''
  - type: vertical-stack
    cards: []
  - type: custom:mushroom-template-card
    primary: Heizung
    secondary: ''
    icon: ''
  - type: vertical-stack
    cards: []
  - type: custom:mushroom-template-card
    primary: Sonstiges
    secondary: ''
    icon: ''
  - type: vertical-stack
    cards: []
```
