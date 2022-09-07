# Autofocus und Autohelligkeit ausschalten

## Funktionsmöglichkeiten der Kamera herausfinden:

```
v4l2-ctl --list-ctrls 
```



## Prüfen ob die Befehle richtig umgesetzt werden

Dieses Beispiel zeigt die Deaktivierung des Autofokus durch das setzen des Wertes <mark style="background-color:red;">**0**</mark>.

```
v4l2-ctl --set-ctrl=focus_auto=0 
```

Setzt den Focus Manuell auf den eingebenden Wert. Hier ist es 20

```
v4l2-ctl --set-ctrl=focus_absolute=20
```

Schaltet die Autohelligkeit aus.

```
v4l2-ctl --set-ctrl=exposure_auto=0
```

## Übertragung in Autostart

Bearbeiten der crowsnest.conf

```
v4l2ctl: focus_auto=0,focus_absolute=5,exposure_auto=1,exposure_absolute=1000,zoom_absolute=100
```
