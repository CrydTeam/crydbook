# Printer is not ready

* Verbindung mit Putty aufbauen

```
 ls /dev/serial/by-id
```

_Beispiel Ausgabe : "usb-1a86\_USB\_Serial-if00-port0"_

Diesen Port in eurer **Printer.cfg** eingragen

_Beispiel:_

```
[mcu]
serial: /dev/serial/by-id/usb-1a86_USB_Serial-if00-port0
restart_method: command
```

{% embed url="https://youtu.be/HzYVKNzeW8w" %}
