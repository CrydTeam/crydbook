# Bltouch

### Bltouch Test Macro

* Macro downloaden und einbinden\
  \-[ Link zur Config](https://github.com/cryd-s/Vyper\_extended/blob/main/GCODES/bltouch\_test.cfg)\
  \- in printer.cfg einbinden `[include bltouch_test.cfg]`
* Testmakro über die Konsole oder Makrobutton starten\
  `BLT_Test`

1. Pin fährt aus
2. Pin fährt ein
3. Pin fährt aus und aktiviert Touch mode
4. Pin unten und Status wird abgefragt. **"Open"** ist richtig
5. Pin muss manuell mit dem Finger ausgelöst werden. **"Triggered"** ist richtig

{% hint style="info" %}
Bei einigen Bltouch Modellen kommt es vor, dass diese Auslösen nicht erkannt wird. Dann bitte folgenden tun:

&#x20;\- Drucker manuell ins obere Drittel drehen\
&#x20;\- G28 aktivieren (Homen)\
&#x20;\- Bei Z-Achse mit dem Finger den Bltouch betätigen und prüfen, ob der Drucker stehen      bleibt. Wenn nein **NOT-AUS**.
{% endhint %}

### Konsolenbefehle

{% tabs %}
{% tab title="Pin ausfahren" %}
`BLTOUCH_DEBUG COMMAND=pin_down`
{% endtab %}

{% tab title="Pin einfahren" %}
`BLTOUCH_DEBUG COMMAND=pin_up`
{% endtab %}

{% tab title="Touch Mode" %}
`BLTOUCH_DEBUG COMMAND=touch_mode`
{% endtab %}

{% tab title="Status abfrageb" %}
`QUERY_PROBE`
{% endtab %}
{% endtabs %}

