# BlTouch

### **1. Bltouch Sektion in printer.cfg einfügen**

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
