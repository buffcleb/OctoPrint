# OctoPrint
example of adding buttons and sliders to OctoPrint 1.2.9

https://github.com/buffcleb/OctoPrint/raw/master/Screen.Shot.2016-03-02.at.6.47.52.PM.png

This snippet is located below "key:" in the config.yaml and adds support for the BLTouch and a fan control

pi@octopi ~ $ pwd
/home/pi
pi@octopi ~ $ vi .octoprint/config.yaml

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
