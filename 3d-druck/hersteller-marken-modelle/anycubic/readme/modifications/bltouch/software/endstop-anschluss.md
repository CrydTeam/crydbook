# Endstop Anschluss

{% hint style="warning" %}
Achtung. Diese Variante kann Probleme aufweisen.
{% endhint %}

1. Bltouch Sektion in Printer.cfg einfügen

```
#######################################
#              BL Touch               #
#######################################
[bltouch]
sensor_pin: ^PB2
control_pin: PC6
z_offset: 0
x_offset: -53
y_offset: 15
samples: 1
speed: 3
#samples_tolerance: 0.075
#samples_tolerance_retries: 3
#samples_result: average
```

\-----------------------------------------------------------------------------------------------------

2\. Bltouch als Endstop definieren

```
[stepper_z]
step_pin: PB6
dir_pin: !PB5
enable_pin: !PC14
microsteps: 16
rotation_distance: 8
endstop_pin: probe:z_virtual_endstop ; Virtual Probe active
position_max: 260 ; More Movement to the right old250
position_min: -5
homing_speed: 5.0

[stepper_z1]
step_pin: PC0
dir_pin: !PC1
enable_pin: !PC15
microsteps: 16
rotation_distance: 8
```

\-----------------------------------------------------------------------------------------------------

3\. Neuen Homepunkt und Safe Home einrichten

```
[safe_z_home]
home_xy_position: 175.5,100 ; Virtual Probe in the middle of the bed
z_hop: 10
```

\-----------------------------------------------------------------------------------------------------

4\. Alte Probe Sektion löschen (Folgende Abschnitte löschen oder auskommentieren)

<pre><code>#[probe]
#pin: !PB12
#z_offset: 0
#speed: 8.0
#samples: 1
#activate_gcode:
#    probe_reset

#[output_pin probe_reset_pin]
<strong>#pin: PB13</strong></code></pre>

\-----------------------------------------------------------------------------------------------------

5\. Z-Tilt einfügen

```
[z_tilt]
z_positions:
    -30,135
    275,135
points:
    60,105
    260,105
speed: 140
horizontal_move_z: 7
retries: 7
retry_tolerance: 0.015
```

