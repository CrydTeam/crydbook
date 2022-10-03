# BlTouch

### 1. Bltouch config in printer.cfg einfügen

> _****_[_**Link zur Config**_](https://github.com/cryd-s/Vyper\_extended/blob/main/1\_extended\_board/stealthburner%20toolhead/printer\_stealthburner.cfg)_****_

{% code lineNumbers="true" %}
```json
#######################################
#         PROBE    #Stealthburner     #    
#######################################
[bltouch]
sensor_pin: ^PB12 #pins for extended board c 
control_pin: PB13 #pins for extended board c
#sensor_pin: ^PB13 #pins for extended board a 
#control_pin: PB12 #pins for extended board a
z_offset: 0
x_offset: 0
y_offset: 19
samples: 1
speed: 15
```
{% endcode %}

{% hint style="info" %}
_\_\_Select\_\_ your **#sensor\_pin** and **#control\_pin**_
{% endhint %}

### 2. Hardware Endstops deaktivieren und Virtueller Endstop (Bltouch) aktivieren

```
[stepper_z]
step_pin: PB6
dir_pin: !PB5
enable_pin: !PC14
microsteps: 16
rotation_distance: 8
endstop_pin: probe:z_virtual_endstop
position_max: 240
position_min: -5
homing_speed: 40.0
second_homing_speed: 10.0

[stepper_z1]
step_pin: PC0
dir_pin: !PC1
enable_pin: !PC15
microsteps: 16
rotation_distance: 8
```

### 3. Safe Homing einrichten

Der Drucker homed damit in der Mitte des Druckbettes und hebt vor jedem Home sicherheitshalber den Druckkopf an.

```
[safe_z_home]
home_xy_position: 122.5, 100
speed: 50.0
z_hop: 20
```
