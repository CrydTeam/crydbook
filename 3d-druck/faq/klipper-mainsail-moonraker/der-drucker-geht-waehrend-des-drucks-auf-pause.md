# Der Drucker geht während des Drucks auf Pause

## Häufigste Fehlerquelle:

* Filamentsensor&#x20;

## Lösung

Einfach abstecken und aus der Printer.cfg aus kommentieren.

```
#[filament_switch_sensor runout]
#pause_on_runout: True
#switch_pin: PA5
```
