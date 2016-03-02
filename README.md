# OctoPrint
example of adding buttons and sliders to OctoPrint 1.2.9

appearance: {}
controls:
- children:
  - command: M280 P0 S120
    name: Self Test
  - command: M280 P0 S160
    name: Alarm Release
  - command: M280 P0 S90
    name: Pin Up
  - command: M280 P0 S10
    name: Pin Down
  layout: horizontal
  name: BLTouch
- children:
  - command: M106 S%(speed)s
    input:
    - default: 255
      name: Speed (0-255)
      parameter: speed
      slider:
        max: 255
        min: 0
    name: Enable Fan
  - command: M107
    name: Disable Fan
  layout: horizontal
  name: Fan

Output ::::

[...]
Send: M106 S145
Recv: ok
[...]
Send: M106 S140
Recv: ok
[...]
Send: M106 S255
Recv: ok
Send: M107
Recv: ok
