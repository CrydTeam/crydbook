---
description: wir verwenden hier eine Mushroom Template Card
---

# Room Cards

<figure><img src="../../../../../.gitbook/assets/image (3) (1).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Icon Farbe basierend auf Gruppenstatus (alle Lichter und Geräte als Helfer kombiniert)
{% endhint %}

```
{% raw %}
{% if is_state('light.lichter_wohnzimmer', 'on') %}
  orange
{% endif %}
{% endraw %}
```



{% hint style="info" %}
Raumstatus anzeige - Temperatur und Luftfeuchtigkeit:
{% endhint %}

```
{{ states('sensor.STATUS_1') }} °C / {{ states('sensor.STATUS_2') }} % 
```

<figure><img src="../../../../../.gitbook/assets/image (1) (2).png" alt=""><figcaption></figcaption></figure>
