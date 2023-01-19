# Custom Utility Scripts

##  1. `gamemode_on`: Gamemode Toggler - On
  - Disables XFCE compositor to improve framerate
  - Turns off the output from the left and right monitor in order to ensure Nvidia GSync can run
    - Run `xrandr` to see which monitors are connected and which portion of the screen they render

## 2. `gamemode_off`: Gamemode Toggler - Off
  - Enables XFCE compositor
  - Reapplies saved display configuration profile to re-enable monitors and proper render positions

## 3. `gamemodestream_on`: Game Streaming Mode Toggler - On
  - Disables XFCE compositor to improve framerate
  - Turns off the output from the left and right monitor in order to properly place rendering/encode to sunshine
    - Run `xrandr` to see which monitors are connected and which portion of the screen they render
  - Turns off GSync
  - Sets NIC to 100MB/s full duplex (fixes intermittent stuttering issues)
  - Ensures sunshine caps are on

## 4. `gamemodestream_off`: Game Streaming Mode Toggler - Off
  - Enables XFCE compositor
  - Reapplies saved display configuration profile to re-enable monitors and proper render positions
  - Turns on GSync
  - Sets NIC to 1000MB/s full duplex
  - Ensures sunshine caps are off

## 5. `swkvm`: Software KVM
  - A script to change the display input with software via ddcutil
  - To get configuration options run `ddcutil detect` to determine which displays are numbered what
  - To determine which hex value maps to which input source run `ddcutil vcpinfo --display=<num> --verbose 60`

#### Usage: `swkvm <number>`

Configuration file should live at `~/.config/swkvm/<number>` in the following format:
```
<display num>:<hex for display input>
<display num>:<hex for display input>
```

Example Configuration:

```
1:0x11
2:0x0f
3:0x0f
```
