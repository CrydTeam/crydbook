# Extruder Sensor anpassen

In der Printer.cfg muss der passende Sensor zum Extruder ausgewählt werden.\


Diese Sensoren stehen zur Auswahl. Bei dem Passenden Sensor die **"#"** entfernen.

```
#sensor_type: Trianglelab-NTC100K-B3950 #trianglelab V6
#sensor_type: ATC Semitec 104GT-2 #most V6 Clones
#sensor_type: ATC Semitec 104NT-4-R025H42G #revo micro
```

```
[extruder]
step_pin: PB4
dir_pin: !PB3
enable_pin: !PA15
microsteps: 16
rotation_distance: 22.5961632003  #has to calibrate
gear_ratio: 50:17
full_steps_per_rotation: 200
nozzle_diameter: 0.400
filament_diameter: 1.750
heater_pin: PA1
#sensor_type: Trianglelab-NTC100K-B3950 #trianglelab V6
#sensor_type: ATC Semitec 104GT-2 #most V6 Clones
#sensor_type: ATC Semitec 104NT-4-R025H42G #revo micro
sensor_pin: PC4
control = pid 
pid_kp = 43.209 #has to calibrate
pid_ki = 7.386 #has to calibrate
pid_kd = 63.194 #has to calibrate
min_temp: 0
max_temp: 280
max_extrude_cross_section: 50.0

############################################
# Custom Sensoren
############################################
[thermistor Trianglelab-NTC100K-B3950]
temperature1: 25
resistance1: 103180
temperature2: 150
resistance2: 1366.2
temperature3: 250
resistance3: 168.6
```

{% hint style="warning" %}
Nach dem Wechsel des Hotends ist ein neues PID Tuning für den Extruder erforderlich.
{% endhint %}

{% embed url="https://www.youtube.com/watch?v=8h9hYSACWhc" %}
