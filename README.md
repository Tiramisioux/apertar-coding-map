# Apertar coding map

An interactive map of the [Apertar](https://github.com/Apertar-Studio) camera software (Tiramisioux's fork), for people who
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

- **Pink `fork` tags** mark what only Tiramisioux's fork has: per box, the number of fork-only
  commits touching its files (with the newest ones and a compare link), and code lines or example
  steps that upstream doesn't have.

The code shown is from Tiramisioux's fork, branch `cinemate-port`
([Apertar-Core](https://github.com/Tiramisioux/Apertar-Core/tree/cinemate-port),
[Apertar-UI](https://github.com/Tiramisioux/Apertar-UI/tree/cinemate-port)), and the
[imx585 driver](https://github.com/Tiramisioux/imx585-v4l2-driver/tree/apertar) (branch `apertar`).
Upstream is [Apertar-Studio](https://github.com/Apertar-Studio). JSON examples are shortened with `…`.

## Files

`index.html` is the whole page: no build step, no dependencies besides two Google Fonts.
Open it locally in a browser, or serve the folder with any static server.
