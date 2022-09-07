# Bed Mesh

Nachdem ihr erfolgreich die Schrauben grob mit dem `SCREWS_TILT_CALCULATE` geht das Feintuning jetzt mit dem Bedmesh weiter.

{% hint style="info" %}
Bitte vorher ein Z-Tilt ausführen. `Z_TILT_ADJUST`
{% endhint %}

Wenn ihr das gemacht habt empfehlen wir euch mit einem Bedmesh 7x7 und einem Ref-Index von 24 zu beginnen.

<pre><code><strong># Bed mesh Config für Stealthburner
</strong><strong>
</strong><strong>[bed_mesh]
</strong>mesh_min: 10,13
mesh_max: 235, 240
probe_count: 7,7
#mesh_pps: 2,3
algorithm: bicubic
speed: 150
horizontal_move_z: 8
relative_reference_index: 24</code></pre>
