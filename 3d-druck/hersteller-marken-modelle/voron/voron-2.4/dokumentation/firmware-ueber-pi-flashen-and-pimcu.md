---
description: Quelle Voron Discord Nutzer Hagbard V2.1070
---

# Firmware über Pi Flashen & PiMCU

[Quellenlink](https://discord.com/channels/460117602945990666/460819549202284553/906967705616265285)

**Octopus Fimware flashen:** \
Nur für Updates, wenn schon mal Klipper drauf war! \
Für das erste mal flashen diese Anleitung befolgen:\
&#x20;[https://github.com/bigtreetech/BIGTREETECH-OCTOPUS-V1.0/tree/master/Firmware/Klipper#build-firmware-image](https://github.com/bigtreetech/BIGTREETECH-OCTOPUS-V1.0/tree/master/Firmware/Klipper#build-firmware-image) \
\
\
Mit ssh auf dem Pi einloggen.

```
sudo service klipper stop

cd klipper
make clean
make menuconfig
```

Wie hier einstellen. [https://github.com/bigtreetech/BIGTREETECH-OCTOPUS-V1.0/tree/master/Firmware/Klipper#build-firmware-image](https://github.com/bigtreetech/BIGTREETECH-OCTOPUS-V1.0/tree/master/Firmware/Klipper#build-firmware-image) \
\
Mit 'Q' beenden und mit 'Y' bestätigen.

```
make
make flash FLASH_DEVICE=/dev/serial/by-id/<ID von deinem Board>
```

Die ID von deinem Board findest du über

```
ls /dev/serial/by-id
```

heraus. Oder du drückst nach "by-id" einfach Tab. Sie sieht so ähnlich aus:

```
usb-Klipper_stm32f446xx_0E002B00135053424E363620-if00
```

**RPi MCU flashen:**

```
make clean
make menuconfig
```

Unter Microcontroller Architecture "Linux process" wählen. Mit 'Q' beenden und mit 'Y' bestätigen.

```
make
make flash

sudo service klipper start
```

Fertig (Bearbeitet)Springen
