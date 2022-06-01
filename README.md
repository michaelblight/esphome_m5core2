# esphome_m5core2
My attempt at getting the m5core2 to work with esphome.

This works if you power off the core2 and power it back on.  But if it reboots or you press the reset button the display stops.   Let me know if you get further!

Modifications from fork:
* Moved 'custom_components' to 'components' so that it is compatible with `external_components`, as in
```
    external_components:
    - source: 
        type: git
        url: https://github.com/michaelblight/esphome_m5core2
        username: !secret git_username
        password: !secret git_token
        components: [ axp192, ili9342 ]
        refresh: 60s
```
* Changed battery level config in `axp192/sensor.py` (as a result of a breaking change in ESPHome?)