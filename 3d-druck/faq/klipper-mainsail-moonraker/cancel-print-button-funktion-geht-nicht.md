# Cancel print button/Funktion geht nicht

Dieses Makro in eurer **mainsail.cfg** tauschen und in den Settings den "cancel print button" an machen.

<pre><code>[gcode_macro CANCEL_PRINT]
description: Bricht den aktuellen Druck ab
rename_existing: CANCEL_PRINT_BASE
variable_park: True
gcode:
  ## Move head and retract only if not already in the pause state and park set to true
  {% if printer.pause_resume.is_paused|lower == 'false' and park|lower == 'true'%}
    _TOOLHEAD_PARK_PAUSE_CANCEL
  {% endif %}
  TURN_OFF_HEATERS
  CANCEL_PRINT_BASE

<strong>
</strong><strong>######################################################################
</strong># Druckkop Parkbefehl
######################################################################

[gcode_macro _TOOLHEAD_PARK_PAUSE_CANCEL]
description: Helper: Parkposition im PAUSE and CANCEL_PRINT
variable_extrude: 1.0
gcode:
  ##### set park positon for x and y #####
  # default is your max posion from your printer.cfg
  {% set x_park = printer.toolhead.axis_maximum.x|float - 5.0 %}
  {% set y_park = printer.toolhead.axis_maximum.y|float - 5.0 %}
  {% set z_park_delta = 2.0 %}
  ##### calculate save lift position #####
  {% set max_z = printer.toolhead.axis_maximum.z|float %}
  {% set act_z = printer.toolhead.position.z|float %}
  {% if act_z &#x3C; (max_z - z_park_delta) %}
    {% set z_safe = z_park_delta %}
  {% else %}
    {% set z_safe = max_z - act_z %}
  {% endif %}
  ##### end of definitions #####
  {% if printer.extruder.can_extrude|lower == 'true' %}
    M83
    G1 E-{extrude} F2100
    {% if printer.gcode_move.absolute_extrude |lower == 'true' %} M82 {% endif %}
  {% else %}
    {action_respond_info("Extruder not hot enough")}
  {% endif %}
  {% if "xyz" in printer.toolhead.homed_axes %}
    G91
    G1 Z5 F900
    G90
    G1 X{x_park} Y{y_park} F6000
    {% if printer.gcode_move.absolute_coordinates|lower == 'false' %} G91 {% endif %}
  {% else %}
    {action_respond_info("Printer not homed")}
  {% endif %}
</code></pre>

<figure><img src="../../../.gitbook/assets/cancle_print.jpg" alt=""><figcaption><p>Cancle Print Activation</p></figcaption></figure>

## Zusätzliche Makros

```
######################################################################
# Druckpause
######################################################################

[gcode_macro PAUSE]
description: Pausiert den aktiellen Druck
rename_existing: PAUSE_BASE
# change this if you need more or less extrusion
variable_extrude: 1.0
gcode:
    ##### read E from pause macro #####
    {% raw %}
{% set E = printer["gcode_macro PAUSE"].extrude|float %}
    ##### set park positon for x and y #####
    # default is your max posion from your printer.cfg
    {% set x_park = printer.toolhead.axis_maximum.x|float - 5.0 %}
    {% set y_park = printer.toolhead.axis_maximum.y|float - 5.0 %}
    ##### calculate save lift position #####
    {% set max_z = printer.toolhead.axis_maximum.z|float %}
    {% set act_z = printer.toolhead.position.z|float %}
    {% if act_z < (max_z - 2.0) %}
        {% set z_safe = 2.0 %}
    {% else %}
        {% set z_safe = max_z - act_z %}
    {% endif %}
    {%set min_extrude_temp = printer.configfile.settings["extruder"]["min_extrude_temp"]|int %}
    {%set act_extrude_temp = printer.extruder.temperature|int %}
    ##### end of definitions #####
    PAUSE_BASE
    G91
    {% if act_extrude_temp > min_extrude_temp %}
      G1 E-{E} F2100
    {% else %}
      {action_respond_info("Extruder not hot enough")}
    {% endif %}
    {% if "xyz" in printer.toolhead.homed_axes %}
      G1 Z{z_safe} F900
      G90
      G1 X{x_park} Y{y_park} F6000
    {% else %}
      {action_respond_info("Printer not homed")}
    {% endif %}
{% endraw %} 
```

```
#####################################
# END PRINT                         #
#####################################

[gcode_macro END_PRINT]
description: All what needs to be done at print end
gcode:
    M117 Turn off Heaters
    TURN_OFF_HEATERS                         ; Turn off bed and nozzle
	G91                                      ; Relative positioning
    SET_GCODE_OFFSET Z_ADJUST=+0.06
	M117 Retract
    G1 E-1 F3000                             ; Retract
	G1 X-0.5 Y-0.5 Z20 E-5                    ; Move a bit and retract filament even more
	G90                                      ; Absolute positioning
	G1 X0 Y180 Z35 F2200                         ; Move bed to front
	M107                                     ; Turn off part fan
	M84                                      ; Steppers off
	G90                                      ; Absolute positioning
	M117 Print done                          ; Send finish to display
```

```
######################################################################
# DDruckwiederaufnahme
######################################################################
    
[gcode_macro RESUME]
description: Setzt den aktuellen Druck fort
rename_existing: RESUME_BASE
gcode:
    ##### read E from pause macro #####
    {% raw %}
{% set E = printer["gcode_macro PAUSE"].extrude|float %}
    {%set min_extrude_temp = printer.configfile.settings["extruder"]["min_extrude_temp"]|int %}
    {%set act_extrude_temp = printer.extruder.temperature|int %}
    #### get VELOCITY parameter if specified ####
    {% if 'VELOCITY' in params|upper %}
      {% set get_params = ('VELOCITY=' + params.VELOCITY)  %}
    {%else %}
      {% set get_params = "" %}
    {% endif %}
    ##### end of definitions #####
    {% if act_extrude_temp > min_extrude_temp %}
      G91
      G1 E{E} F2100
    {% else %}
      {action_respond_info("Extruder not hot enough")}
    {% endif %}
{% endraw %}  
    RESUME_BASE {get_params}
```
