# Neopixel Einrichten und Nutzen

Habt Ihr Probleme bei der Einrichtung oder Benutzung euer Neopixel. Dann zeigen wir euch wie alles funktioniert.\
\


## Konfiguration in Klipper einbinden

Folgende Konfiguration müsst ihr in eure printer.cfg inkludieren oder direkt einfügen.\
\
[Link zur Config](https://github.com/cryd-s/Vyper\_extended/blob/main/GCODES/neopixel/neopixel\_pin.cfg)

### Pin (Schnittstelle) definieren:

```
[neopixel sb_leds]
pin: 
```

Mit dem Parameter "pin" definiert Ihr die Schnittstelle zu eueren LED. Diesen müsst ihr natürlich für euer Board entsprechend rausfinden.\
\
Für den Vyper gilt zum Beispiel:\
Extended Board am Toolhead -> pin: PA13\


### Wie viele LEDs sind vorhanden

<pre><code>[neopixel sb_leds]
<strong>chain_count: 3</strong></code></pre>

In diesem Beispiel besteht der LED Strand aus insgesamt 3 LEDs.\


### Welche LEDs sind verbaut

```
[neopixel sb_leds]
color_order: GRBW
```

Hier müsst ihr schauen, was Ihr euch gekauft hat. Grundlegend gibt es zwei Typen.\
**WS2812B** = GRB und **SK6812 =** GRBW.

### Farbe bei Hochfahren

```
initial_RED: 0.0
initial_GREEN: 0.0
initial_BLUE: 0.0
initial_WHITE: 0.0
```

Mit diesen Werten könnt ihr die Farbe nach dem Boot festlegen. Setzt dafür einfach den wer zwischen 0.0 und 1.0. In der Regel nimmt man 0.0 für aus und 1.0 für ein.

## Ansteuerung

### Konsolenbefehl zur Anteuerung

`SET_LED LED=sb_leds RED=1 GREEN=1 BLUE=0 WHITE=0 INDEX=1 TRANSMIT=1`

* LED= Name eurer Neopixel Schnittstelle (\[neopixel sb\_leds]). Hier sb\_leds
* RED|GREEN|BLUE|WHITE = Farbe ein oder aus ( 1 oder 0)
* INDEX= Welche LED im Strand soll angesteuert werden

In dem oben genannten Beispielt wird die LED 1 mit der Farbe Gelb angesteuert (Rot + Grün)\
\
Hier sind einige Farbbeispiele in einer Konfig. hinterlegt. ([Neopixel - Farben](https://github.com/cryd-s/Vyper\_extended/blob/main/GCODES/neopixel/neopixel\_farben.cfg))

### Statusmeldungen im Gcode

Link zur [Statusmeldung-Konfiguration](https://github.com/cryd-s/Vyper\_extended/blob/main/GCODES/neopixel/neopixel\_status.cfg)

Hier könnt ihr folgende Meldungen einfach in einen Gcode eurer Wahl einbinden.\


```
# The following status macros are available:
#    STATUS_READY
#    STATUS_OFF
#    STATUS_BUSY
#    STATUS_HEATING
#    STATUS_LEVELING
#    STATUS_HOMING
#    STATUS_CLEANING
#    STATUS_MESHING
#    STATUS_CALIBRATING_Z
# With additional macros for direct control:
#    SET_NOZZLE_LEDS_ON
#    SET_LOGO_LEDS_OFF
#    SET_NOZZLE_LEDS_OFF
```

\
