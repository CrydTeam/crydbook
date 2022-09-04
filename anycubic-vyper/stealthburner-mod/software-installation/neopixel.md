# Neopixel

1. Neopixel in macros.cfg einbinden

```json
[neopixel sb_leds]
pin: PA13
chain_count: 3
color_order: GRBW #SK6812 (Options are GRBW or RGBW)
#color_order: GRB #WS2812B (Options are GRB,RGB, BRG, BGR)
initial_RED: 0.0
initial_GREEN: 0.0
initial_BLUE: 0.0
initial_WHITE: 0.0
```

{% hint style="info" %}
Select the `color_order` für your LEDs
{% endhint %}
