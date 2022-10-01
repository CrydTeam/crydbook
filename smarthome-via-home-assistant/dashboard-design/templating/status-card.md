---
description: wir verwenden hier eine Mushroom Template Card
---

# Status Card

<figure><img src="../../../.gitbook/assets/image (7).png" alt=""><figcaption><p>auf Basis von Werten färbe ich hier die Icons</p></figcaption></figure>

<img src="../../../.gitbook/assets/image (4).png" alt="" data-size="original"><img src="../../../.gitbook/assets/image (5).png" alt="" data-size="original">

```
{% raw %}
{% set s = states('sensor.total_power')|int %}
{% if s < 250 %}
  green
{% elif s < 500 %}
  orange
{% elif s > 500 %}
  red
{% else %}
{% endif %}
{% endraw %}
```

<figure><img src="../../../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>
