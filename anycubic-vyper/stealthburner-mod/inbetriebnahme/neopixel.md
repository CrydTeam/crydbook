# Neopixel

### Neopixel Config einfügen und aktivieren

* [Link zur Config ](https://github.com/cryd-s/Vyper\_extended/blob/main/GCODES/neopixel/neopixel\_pin.cfg)
* in printer.cfg einbinden `[include neopixel_pin.cfg]`
* In Config die passende LED als _**#color\_order** auswählen._

__

### Neopixel Status Config einfügen und aktivieren

* [Link zur Config ](https://github.com/cryd-s/Vyper\_extended/blob/main/GCODES/neopixel/neopixel\_status.cfg)
* in printer.cfg einbinden `[include` neopixel\_status.cfg`]`
* Status kann in Macros eingebaut werden. Zum Beispiel `STATUS_READY`

### Neopixel Farben Config einfügen und aktivieren

* [Link zur Config ](https://github.com/cryd-s/Vyper\_extended/blob/main/GCODES/neopixel/neopixel\_farben.cfg)
* in printer.cfg einbinden `[include` neopixel\_farben.cfg`]`

Led Ansteuerung über folgenden Befehl:\
\
`SET_LED LED=sb_leds RED=1 GREEN=1 BLUE=0 WHITE=0 INDEX=1 TRANSMIT=1`

{% tabs %}
{% tab title="LED=" %}
`Name des in der Neopixel vergeben macros`
{% endtab %}

{% tab title="RED/GREEN/BLUE/WHITE=" %}
**An** und **Ab**wählen einer Farbe mit **0** oder **1**
{% endtab %}

{% tab title="INDEX=" %}
Welche LED soll angesteuert werden. Da 3 Stück verbaut kann hier 1-3 gewählt werden
{% endtab %}

{% tab title="TRANSMIT=" %}
Ausführung direkt.
{% endtab %}
{% endtabs %}



