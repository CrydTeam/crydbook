---
description: wir verwenden hier eine Mushroom Template Card
---

# On/Off Card

<figure><img src="../../../.gitbook/assets/image (3) (1) (3).png" alt=""><figcaption><p>individuelle Statusanzeige und Einfärbung</p></figcaption></figure>

{% hint style="info" %}
Mit diesem Code kann eine einfache Einfärbung der Template Card bei Status "on" hinterlegt werden.
{% endhint %}

```
{% raw %}
{% if is_state('switch.alle_gerate_ohne_3d_drucker', 'on') %}
  orange
{% endif %}
{% endraw %}
```





{% hint style="info" %}
Hiermit könnt ihr aus "on" ein einfaches "An" bzw. "Aus" generieren (z.B. on = offen / off = geschlossen)
{% endhint %}

```
{% raw %}
{% if is_state('switch.alle_gerate', 'on') %}
  An
{% else %}
  Aus
{% endif %}
{% endraw %}
```

<figure><img src="../../../.gitbook/assets/image (8) (2).png" alt=""><figcaption></figcaption></figure>

