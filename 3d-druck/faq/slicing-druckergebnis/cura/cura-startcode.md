---
description: 'Cura Startcode V2.0 / worked with and without BLTouch:'
---

# Cura Startcode

## Start Code

```
G21                        ; set units to millimeters
G90                        ; Set all axes to absolute
M82                        ; set extruder to absolute mode
M107                        ; start with the fan off
M140 S{material_bed_temperature_layer_0}     ; Start heating the bed
G4 S60                        ; wait 1 minute
M104 S{material_initial_print_temperature}    ; start heating the hot end
M190 S{material_bed_temperature_layer_0}    ; wait for bed
M109 S{material_initial_print_temperature}    ; wait for hotend
M300 S1000 P500                    ; BEEP heating done
G28                        ; move X/Y to min endstops
M117 Bis JETZT ist alles gut!!!
G1 X0 Y-5 F2200                    ; Go to front
G0 Z0.15                                        ; lift nozzle a bit 
G92 E0                                          ; zero the extruded length 
G1 X50 E25 F500                                 ; Extrude 25mm of filament in a 5cm line. 
G92 E0                                          ; zero the extruded length again 
G1 E-2 F500                                     ; Retract a little 
G1 X120 F4000                                   ; Quickly wipe away from the filament line
```

## End Code

```
END_PRINT
```
