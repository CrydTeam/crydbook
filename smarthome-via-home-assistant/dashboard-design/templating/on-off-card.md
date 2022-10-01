---
description: wir verwenden hier eine Mushroom Template Card
---

# On/Off Card

<figure><img src="../../../.gitbook/assets/image (3).png" alt=""><figcaption><p>individuelle Statusanzeige und Einfärbung</p></figcaption></figure>

```
{% raw %}
{% if is_state('switch.alle_gerate_ohne_3d_drucker', 'on') %}
  orange
{% endif %}
{% endraw %}
```

Mit diesem Code kann eine einfache Einfärbung der Template Card bei Status "on" hinterlegt werden.

```
{% raw %}
{% if is_state('switch.alle_gerate', 'on') %}
  An
{% else %}
  Aus
{% endif %}
{% endraw %}
```

Hiermit könnt ihr aus "on" ein einfaches "An" bzw. "Aus" generieren (z.B. on = offen / off = geschlossen)

<figure><img src="../../../.gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>

