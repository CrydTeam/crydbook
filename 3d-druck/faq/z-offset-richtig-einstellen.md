# Z-Offset richtig einstellen

Ihr habe den PROBE\_CALIBRATE durchgeführt und nach dem ACCEPT mit einem klicken auf SAVE\_CONFIG eure Config gespeichert ?&#x20;

Sehr gut ... doch wie geht es nun weiter ?



Nun ist es daran, euren Z-Offset Live "On the Fly" fein zu tunen, mit den sogenannten Babysteps.

Als erstes erstellt Ihr euch im SuperSlicer eine Datei, die die Höhe eurer ersten Schicht hat. Dafür geht Ihr mit Rechtsklick auf die Baufläche im SuperSlicer und fügt eine Form (Box) hinzu.

<figure><img src="../../.gitbook/assets/image (2).png" alt=""><figcaption><p>Rechtsklick auf die Baufläche </p></figcaption></figure>

Nun müsst Ihr die Höhe eurer ersten Schicht aus dem Slicer ermitteln. (hier bsp. anhand des SuperSlicer)

<figure><img src="../../.gitbook/assets/image (3).png" alt=""><figcaption><p>Druckeinstellungen -> Slice -> Höhe der ersten Schicht</p></figcaption></figure>

Die folgenden Einstellungen müssen nun noch im Slicer vorgenommen werden, damit Ihr die richtigen Maße für die Form habt.

* Als erstes Klickt Ihr auf der rechten Seite auf das Schloss. Dies sollte nun "offen" dargestellt werden.
* Als zweites tragt Ihr die Werte (je nach Bettgröße oder bedarf) ein. Wichtig ist, das der letzte Punkt eurer ersten Schichthöhe entspricht. (in meinem Fall, 0.24mm)

<figure><img src="../../.gitbook/assets/image (11).png" alt=""><figcaption><p>Abmaße der Form einstellen</p></figcaption></figure>

Nun kann die Datei geslicet und an den Drucker geschickt werden.

Beginnt nun mit dem Drucken und stellt den Offset Live über Mainsail ein. Dies geschieht über diese Toolbar&#x20;

<figure><img src="../../.gitbook/assets/image (1).png" alt=""><figcaption><p>Toolbar Z-Versatz</p></figcaption></figure>

Wenn Ihr nun soweit seid, dass Ihr die für euch beste Einstellung gefunden habt, ist es sehr wichtig, dass Ihr die Config erneut abspeichert.

Geht dafür einfach über den Save Config Button oben rechts neben dem NOTAUS, oder schreibt SAVE\_CONFIG in die Konsole und bestätigt mit Enter.

Die Firmware sollte nun einmal Neustarten.
