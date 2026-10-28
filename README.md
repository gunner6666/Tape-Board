# Tape Board

**A copper-tape circuit designer for 3D printed boards.**

Tape Board lets you design a simple circuit board, then 3D print it. You print the plate, press copper tape onto the raised lines, and solder component legs through the holes. No etching, no chemicals, and no PCB fab order.

Works on **Windows** and **Android**.

Created by R. Heller · [☕ Support on Buy Me a Coffee](https://buymeacoffee.com/Rheller82)

---

## Download

Open the **Releases** page and grab the file for your device:

| Device | File |
| --- | --- |
| Windows (installer) | `Tape-Board-1.0.0-x64.exe` |
| Windows (portable, no install) | the portable `.exe` |
| Android | `Tape-Board.apk` |

**Windows:** the app is not code-signed, so Windows SmartScreen may say "Windows protected your PC". Click **More info**, then **Run anyway**.

**Android:** when you open the APK, allow "install unknown apps" for your browser or file manager.

---

## How it works

1. Lay out parts and copper-tape runs on a grid-snapped board, by hand or automatically.
2. Export an **STL** file.
3. Print the plate. The STL has raised lines where the tape goes (or grooves, if you prefer), plus through-holes for pins.
4. Press copper tape onto the lines and solder the parts in.

---

## Features

- **Hand drawing:** place parts, draw tape runs, drag corners to reshape them, and undo with Ctrl+Z.
- **Auto-generate:** describe your circuit as a short text list and the app places the parts and routes the tape for you.
- **Confirm before you commit:** each change can wait for approval so you can nudge it into position first.
- **Grid snapping:** presets from 5.08 mm down to 0.1 mm, or any custom size.
- **Tape controls:** widths from 0.5 mm to 6 mm, with 90°-only, 45° and 90°, or any-angle runs.
- **Per-part hole and pad sizes:** give any part its own pin hole and solder pad size.
- **Import KiCad footprints:** bring in parts that aren't in the built-in list.
- **Save and open designs** so you can come back to a board later.
- **Works on phone and desktop** with the same design.

---

## Quick start

1. Choose a part such as **Resistor** from the Parts list, then tap or click the board to place it. Press **Confirm** (or Enter) to keep it.
2. Pick the **Tape** tool. Click where the tape starts, then where it ends. **Confirm** keeps that piece. **Extend** keeps it and carries on from where it ended.
3. Press **Export STL** and print the file.

---

## Tools

| Tool | Shortcut | What it does |
| --- | --- | --- |
| Tape | T | Draw copper tape runs |
| Part | P | Place the selected part |
| Move | V | Drag a part, a tape run, or a hole |
| Select | S | Pick a part and give it its own hole and pad size |
| Rotate | R | Turn a part 90° around its first pin |
| Hole | H | Add a mounting screw hole |
| Erase | X | Remove a part, hole, or tape run |

Scroll to zoom, hold the middle mouse button to pan, and use **Fit** to reset the view.

---

## Auto-generate

Instead of drawing by hand, describe your circuit as a text list. There are two kinds of line.

**Part lines** give each part a name and a type:

```
J1 h2
R1 res
D1 led
```

**Connection lines** list the pins that must be joined with tape:

```
VCC: J1.1 R1.1
N1:  R1.2 D1.1
GND: D1.2 J1.2
```

That is a battery, a resistor, and an LED in a loop. Click **Generate layout** and the app arranges the parts, tries many orientations, and routes tape so that it never crosses other tape or touches other pads. Run it again for a different arrangement.

Lines that start with `#` are notes and are ignored.

### Built-in part types

| Type | What it is |
| --- | --- |
| `pad` | A single solder pad or wire point |
| `res` | Resistor or any two-legged part with 10.16 mm spacing, such as a diode |
| `led` | LED with 2.54 mm leg spacing (pin 1 is +, pin 2 is −) |
| `h2` `h3` `h4` `h6` `h8` | A single row of 2.54 mm pins: battery connectors, switches, buttons, sensors |
| `dip8` `dip14` `dip16` | DIP chips with rows 7.62 mm apart |
| `esp32` `enc` `tp4056` | ESP32 board, rotary encoder, and TP4056 charger module |

The **Load an example** menu has ready-made boards, including an LED with a battery, two LEDs with their own resistors, an 8-pin chip with an LED, and an ESP32 with an encoder, TP4056, and battery.

---

## Print settings

| Setting | What it controls |
| --- | --- |
| Plate thickness | Thickness of the printed base |
| Traces | **Raised** lines for tape to sit on, or **Lowered** grooves |
| Trace height | How far the lines rise or sink |
| Pin hole ⌀ | Size of the through-holes for component legs |
| Larger solder pads | Optional bigger pads, with their own diameter |

**Export shape** controls the outline of the plate: the whole board, fit to the used area, or cut away unused sections.

---

## Files

- **STL:** the printable plate.
- **SVG template (1:1):** a full-size template you can use to cut or position the tape.
- **Design file (.json):** save a board and open it again later.

---

## Credits

Tape Board was created by **R. Heller**.

If the app is useful to you, you can [buy me a coffee ☕](https://buymeacoffee.com/Rheller82).
