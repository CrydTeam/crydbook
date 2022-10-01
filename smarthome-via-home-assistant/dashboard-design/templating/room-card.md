---
description: wir verwenden hier eine Mushroom Template Card
---

# Room Card

<figure><img src="../../../.gitbook/assets/image.png" alt=""><figcaption><p>Raumverlinkung incl. Farbwechsel und Statusanzeige</p></figcaption></figure>

Icon Farbe basierend auf Gruppenstatus (alle Lichter und Geräte als Helfer kombiniert)

```
{% raw %}
{% if is_state('light.lichter_wohnzimmer', 'on') %}
  orange
{% endif %}
{% endraw %}
```

Raumstatus anzeige - Temperatur und Luftfeuchtigkeit:

```
{{ states('sensor.STATUS_1') }} °C / {{ states('sensor.STATUS_2') }} % 
```

<figure><img src="../../../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>
