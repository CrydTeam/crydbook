---
description: wir verwenden hier eine Mushroom Template Card
---

# Status Card

<figure><img src="../../../../../.gitbook/assets/image (1) (3).png" alt=""><figcaption></figcaption></figure>

```
{% raw %}
{% set s = states('sensor.DEIN_SENSOR')|int %}
{% if s < 250 %}
  green
{% elif s < 300 %}
  orange
{% elif s > 500 %}
  red
{% else %}
{% endif %}
{% endraw %}
```

<figure><img src="../../../../../.gitbook/assets/image (6) (1).png" alt=""><figcaption></figcaption></figure>
