# Sensor.yaml

```
# Gaszähler, kommend von ESPHome, aufbereiten für Energy
- platform: template
  sensors:
    gasverbrauch:
      value_template:  >
          {% raw %}
{% if states('sensor.gasverbrauch_esp') | float == 0 %}
            {{ states('sensor.gasverbrauch') }}
          {% else %}
            {{ states('sensor.gasverbrauch_esp') | float }}
          {% endif %}
{% endraw %}
      unit_of_measurement: m³
      device_class: gas
      attribute_templates:
        state_class: total_increasing
```
