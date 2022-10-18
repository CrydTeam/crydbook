# PV

![](<../../../../../.gitbook/assets/image (1) (4).png>)

```
type: custom:mini-graph-card
entities:
  - sensor.pv_anlage_electrical_measurement
color_thresholds:
  - value: 0
    color: '#ff0000'
  - value: 50
    color: '#ff8800'
  - value: 200
    color: '#90ee90'
align_icon: left
align_state: center
show_points: false
height: 100
hours_to_show: 24
name: Produktion
show:
  graph: true
  name: true
  extrema: true

```

![](<../../../../../.gitbook/assets/image (1) (3).png>)

```
type: energy-solar-graph
```

![](<../../../../../.gitbook/assets/image (2).png>)

```
type: custom:sun-card
```
