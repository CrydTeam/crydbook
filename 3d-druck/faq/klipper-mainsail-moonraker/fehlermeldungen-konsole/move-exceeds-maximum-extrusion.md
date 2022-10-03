# Move exceeds maximum extrusion

Diese Fehlermeldung tritt meist beim Extrudieren von Filament auf. Standardmäßig ist eine Maximale Länge von 50mm einstellt. Wenn ihr jetzt mehr fördern wollt, kann diese Meldung auftreten.&#x20;

### Lösung:

In der printer.cfg den Wert `max_extrude_cross_section:` anpassen.

```
[extruder]
max_extrude_cross_section: 60.0
```
