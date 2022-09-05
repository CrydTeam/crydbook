---
layout: editorial
---

# Screw Tilt Calculate

Hallo, hier findet ihr die Infos zum `SCREWS_TILT_CALCULATE` Befehl.

{% hint style="warning" %}
Diese dienen lediglich als Orientierung und die Benutzung geht auf **eigene Gefahr**.

Daher prüft bitte, ob diese für euren Drucker passen und euch logisch erscheinen.
{% endhint %}

***

## Installation:

1. [screw.cfg](https://github.com/cryd-s/Vyper\_extended/blob/main/GCODES/screw\_tilt\_calculate/screw.cfg) in euer klipper\_config Verzeichnis kopieren
2. in printer.cfg einbinden `[include screw.cfg]`
3. Save\&restart

***

## Befehle:

`SCREWS_TILT_CALCULATE` = Führt das Skript aus `SCHRAUBEN` = Fährt den Kopf weg, sodass man die Schrauben gut erreicht

***

## Auswertung

```
hinten_rechts_aussen : x=210.0, y=203.0, z=2.10030 : adjust CW 00:01
hinten_links_aussen : x=30.0, y=203.0, z=2.12280 : adjust CW 00:03
vorne_rechts_aussen : x=210.0, y=42.0, z=2.08530 : adjust CCW 00:00
vorne_links_aussen (base) : x=30.0, y=42.0, z=2.08780
```

> vorne\_links\_aussen (base) = Bezugspunkt

> hinten\_rechts\_aussen : z=2.10030 : adjust CW 00:01 -> CW im Uhrzeigersinn nachjustieren

> hinten\_links\_aussen : z=2.12280 : adjust CCW 00:03 -> CCW im Gegen-Uhrzeigersinn nachjustieren

> vorne\_rechts\_aussen : z=2.08530 : adjust CCW 00:00 -> passt

***

## Dokumentation

Dokumentationen zu Gcodes oder Klipper findet ihr hier:

[https://www.klipper3d.org/G-Codes.html?h=scre#screws\_tilt\_calculate ](https://www.klipper3d.org/G-Codes.html?h=scre#screws\_tilt\_calculate)[https://www.klipper3d.org/Config\_Reference.html?h=scre#screws\_tilt\_adjust](https://www.klipper3d.org/Config\_Reference.html?h=scre#screws\_tilt\_adjust)

***

CrydTeam
