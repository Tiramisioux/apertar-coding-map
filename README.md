# Apertar coding map

An interactive map of the [Apertar](https://github.com/Apertar-Studio) camera software, for people who
want to change the code: which program owns what, how a command and a picture travel, and which file to
open for each step.

**Open it:** https://tiramisioux.github.io/apertar-coding-map/

## What it shows

- **Two programs on one Raspberry Pi 5.** `apertar-core` (C++, libcamera) owns the sensor, recording,
  the WebUI on port 8000 and the control state. `Apertar-UI` (Qt/QML) is the touch UI and talks to Core
  over the Unix socket `/tmp/apertar-core.sock`.
- **Box colour** = which repo the code is in (Apertar-UI, Apertar-Core, the WebUI inside Core,
  hardware, files).
- **Line** = what moves and how: commands in (thin = a function call inside one program, thick = a
  socket or HTTP message between programs), state coming back (dashed), pictures (thick orange),
  settings passed through `UI.conf` (dotted).
- **Click any box or arrow** for its file path, one real line of code and a tip.
- **Follow a flow:** step through ISO 800 from the touch screen or the WebUI, an encoder turn, one
  frame, or a zebra toggle.

- **Switch between official Apertar and Tiramisioux's fork.** Official
  ([Apertar-Studio](https://github.com/Apertar-Studio), branch `main`) is the default. The fork is
  branch `cinemate-port` of [Apertar-Core](https://github.com/Tiramisioux/Apertar-Core/tree/cinemate-port)
  and [Apertar-UI](https://github.com/Tiramisioux/Apertar-UI/tree/cinemate-port), plus the
  [imx585 driver](https://github.com/Tiramisioux/imx585-v4l2-driver/tree/apertar) (branch `apertar`);
  link to it with `#fork`. Code lines and examples that differ swap with the switch. On the fork side,
  pink `fork` tags show per box how many commits official Apertar doesn't have (newest five and a
  compare link in the panel), and mark fork-only code lines and example steps.

JSON examples are shortened with `…`.

## Files

`index.html` is the whole page: no build step, no dependencies besides two Google Fonts.
Open it locally in a browser, or serve the folder with any static server.
