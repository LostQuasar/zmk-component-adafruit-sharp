# ZMK Adafruit SHARP Memory LCD Display
This repository adds a ZMK shield definition for the [Adafruit Sharp Display Breakout](https://www.adafruit.com/product/3502) refferd to as `adafruit_sharp` using the `&nice_view_spi` to define pins.
![](https://cdn-shop.adafruit.com/970x728/3502-06.jpg)

## Usage
This module is designed to be used with ZMK 4.0+ exclusively.
Example usage in [zmk-conf](https://github.com/LostQuasar/adafruit-sharp-zmk-conf)

`build.yaml`
```
include:
  - board: YOUR_BOARD_HERE
    shield: YOUR_SHIELD_HERE nice_view_adapter adafruit_sharp
    cmake-args: -DCONFIG_ZMK_DISPLAY=y
```
`west.yml`
```
manifest:
  defaults:
    revision: main
  remotes:
    - name: zmkfirmware
      url-base: https://github.com/zmkfirmware
    - name: LostQuasar
      url-base: https://github.com/LostQuasar
  projects:
    - name: zmk
      remote: zmkfirmware
      import: app/west.yml
    - name: zmk-component-adafruit-sharp
      remote: LostQuasar
  self:
    path: config

```

