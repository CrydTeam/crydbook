---
description: Was ist Z-Tilt und Quad Gantry Level (QGL)
---

# Z-Tilt / Quad Gantry Level

### Erklärung

Hier zeige ich euch kurz, was genau die oben genannten Kommandos machen und was der Zweck davon ist.\
\
Kurz gesagt gleicht das Z-Tilt (Für 2 Z-Motoren) und das Quad Gantry Level (4 Motoren) doe Lage der "Gantry" oder auch X Führung des Druckkopfes aus.\
\
Es werden meist die äußeren Punkte des Druckbettes angefahren und so die Achse parallel zum Bett gestellt.

{% hint style="warning" %}
Wichtig: \
Das Druckbett sollte vorher schon parallel zum Gestell oder Boden stehen.
{% endhint %}

### Konsolenausgabe

Dies ist eine Beispielausgabe des QGL:\
\


```
Making the following Z adjustments:
stepper_z = 0.004953
stepper_z1 = -0.000403
stepper_z2 = -0.000520
stepper_z3 = -0.004030

Average: 7.239051

Actuator Positions:
z: 7.234097 z1: 7.239454 z2: 7.239571 z3: 7.243081

Gantry-relative probe points:
0: 7.236478 1: 7.238353 2: 7.239915 3: 7.240540

probe at 250.000,25.000 is z=7.759460
probe at 250.000,225.000 is z=7.760085
probe at 25.000,225.000 is z=7.761647
probe at 25.000,25.000 is z=7.763522
```

`probe at 250.000,25.000 is z=7.759460`\
Wie Ihre sehen könnt werden als ersten die in der Konfiguration definierten Punkte angefahren und in Z-Höhe vermessen.\
\
`Making the following Z adjustments:`\
``Es werden jetzt für die jeweiligen Motoren Änderungen der Z-Höhe vorgenommen und nochmals die Messpunkte angefahren.\
\
Die Wiederholungen sind abhängig von den von euch definierten Toleranz in der Konfiguration in der Variable: \
`retry_tolerance: 0.0075`\


{% hint style="info" %}
Alle Infos zu den Parametern der Konfiguration findet ihr in der Dokumentation von Klipper.
{% endhint %}

**Klipper Dokumentation:**

{% embed url="https://www.klipper3d.org/Config_Reference.html?h=quad#quad_gantry_level" %}
