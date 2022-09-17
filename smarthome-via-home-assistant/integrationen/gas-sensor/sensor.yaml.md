# Sensor.yaml

```
# Gaszähler, kommend von ESPHome, aufbereiten für Energy
- platform: template
  sensors:
    gasincubicmeter:
      value_template:  >
          {% raw %}
{% if states('sensor.gasverbrauch') | float == 0 %}
            {{ states('sensor.gasincubicmeter') }}
          {% else %}
            {{ states('sensor.gasverbrauch') | float }}
          {% endif %}
{% endraw %}
      unit_of_measurement: m³
      device_class: gas
      attribute_templates:
        state_class: total_increasing
```
