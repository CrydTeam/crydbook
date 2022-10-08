# Kioskmode

Erstellt einen Helfer-Schalter mit dem Namen Kioskmode



Danach können wir den Kioskmode aktivieren indem wir folgenden Code im Dashboard ergänzen

```
kiosk_mode:
  entity_settings:
    - entity:
        input_boolean.kioskmode: 'on'
      hide_sidebar: true
      hide_header: true
    - entity:
        input_boolean.kioskmode: 'off'
      hide_sidebar: false
      hide_header: false
```
