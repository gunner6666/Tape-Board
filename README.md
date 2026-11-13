<p align="center">
  <img src="assets/logo.png" alt="Tape Board logo" width="160">
</p>

# Tape Board

**A copper-tape circuit designer for 3D printed boards.**

Tape Board lets you design a circuit board, then 3D print it. You print the plate, press copper tape onto the raised lines, and solder component legs through the holes. No etching, no chemicals, and no PCB fab order.

Works on **Windows** and **Android**.

Created by R. Heller · [☕ Support on Buy Me a Coffee](https://buymeacoffee.com/Rheller82)

---

## New in 1.0.2: cover designs

The big one for this release: boards can now be printed with a **cover**, so the copper tape sits *below* the surface instead of on top of it. The tape is protected, the cover acts like solder mask, part names are engraved right into it, and the finished board looks far more like a real PCB. You still get the easy part of a raised board: the tape goes onto raised lines (or separate strips) on the bench, where it's simple to press down and trim.

There are three new cover designs, all picked from the **Traces** setting:

| Design | What you print | What you get |
| --- | --- | --- |
| **Raised + cover piece** | A base with raised lines, and a cover with openings shaped like the traces | Tape on one side, recessed below a clean top face |
| **Double-sided (two pieces)** | Two pieces that are each other's cover | Tape on **both** sides of the board, copper showing on each face |
| **Double-sided (strips, traces can cross)** | A bottom cover, a top cover, and one flat strip per tape run | Tape on both sides, and top and bottom tape can **cross**, just like a factory double-sided board |

Covers snap on with **round pegs** (plus **clips on the edge** on the single-cover design), so no glue is needed, and the strips have their own small pegs that hold them in place while you put the board together. See the [changelog](#102) for everything else in this release.

---

## Download

Open the **Releases** page and grab the file for your device:

| Device | File |
| --- | --- |
| Windows (installer) | `Tape-Board-Setup-<version>-x64.exe` |
| Windows (portable, no install) | `Tape-Board-Portable-<version>-x64.exe` |
| Android | `Tape-Board.apk` |

**Windows:** the app is not code-signed, so Windows SmartScreen may say "Windows protected your PC". Click **More info**, then **Run anyway**.

**Android:** when you open the APK, allow "install unknown apps" for your browser or file manager.

---

## How it works

1. Lay out parts and copper-tape runs on a grid-snapped board — by hand, from a schematic you draw, or automatically from a text list.
2. Check the design and preview the plate in 3D.
3. Export an **STL** file.
4. Print the plate. The STL has raised lines where the tape goes (or grooves, if you prefer), through-holes for pins, and any engraved text. With one of the cover designs you get a cover too (see [New in 1.0.2](#new-in-102-cover-designs)): print the pieces, tape them, then snap the cover on.
5. Press copper tape onto the lines and solder the parts in.

---

## Features

**Board styles**

- **Raised** lines or **Lowered** grooves for the tape, printed as one plate.
- **Raised + cover piece**: a base plus a cover that leaves the copper recessed below the surface.
- **Double-sided (two pieces)**: tape on both faces, each piece the other's cover.
- **Double-sided (strips)**: tape on both faces that can cross, with each run printed as its own strip between two covers.
- Covers snap on with round pegs (and edge clips on the single cover), no glue. Part names and your own text are engraved into the cover.

**Drawing the board**

- Place parts and draw tape runs on a grid, with undo and redo throughout.
- Confirm mode lets every change wait for approval so you can nudge it into position first — drag the whole piece, or drag a corner dot to reshape a tape run.
- Extend carries a tape run on from where it ended, keeping it as one piece with mitered corners.
- Rotate and flip parts. Tape that ends on a pad follows the part when you move it.
- Pin 1 of every multi-pin part gets a square pad so chips line up, and the square grows to match the tape running onto it.
- Grid presets from 5.08 mm down to 0.1 mm, or any custom size.
- Tape widths with 90°-only or 45° runs.

**Schematic editor**

- Draw the circuit with proper symbols, wire the pins, and let the app build the board from it.
- Give parts values (10k, 100nF, 1N4148) and pick the exact footprint for each one.
- Built-in parts list you can copy into a shopping list.
- A check before building flags name clashes, ground wired to power, unwired parts, open pins and missing values.
- **Generate PCB** builds a fresh board; **Update PCB** keeps your existing layout and only adds, removes and re-links what changed.

**Auto-generate**

- Describe the circuit as a short text list and the app places the parts and routes the tape.
- Tries up to 40 arrangements and keeps the one with the least tape on the smallest board.
- Adds jumper wires automatically where tape would have to cross.

**Checking and previewing**

- Unrouted connections show as dashed yellow lines, like a ratsnest, and disappear as you lay tape.
- **Check design** finds short circuits, copper too close together, tape that is too thin or stops short of a pad, overlapping parts, copper off the board or in a cutout, and holes cutting into copper. Tap an item to zoom to it.
- **3D preview** shows exactly what the STL will be.
- **Tape cut list** gives every run's length, width and number of bends, plus jumper wire lengths, so you can cut tape before you start.

**Finishing**

- Engraved text, plus automatic part names and LED + marks that find their own clear spot.
- Custom board outlines and cutouts, or a plain rectangle with a corner radius.
- Per-part hole and pad sizes.
- Import KiCad footprints (`.kicad_mod` and the older `.mod`).

---

## Quick start

1. Choose a part such as **Resistor** from the Parts list, then tap or click the board to place it. Parts that come in several sizes ask which one you need. Press **Confirm** (or Enter) to keep it.
2. Pick the **Tape** tool. Click where the tape starts, then where it ends. **Confirm** keeps that piece. **Extend** keeps it and carries on from where it ended. **Esc** ends the run.
3. Press **Check design** to catch mistakes.
4. Press **Export STL** and print the file.

---

## Tools

| Tool | Shortcut | What it does |
| --- | --- | --- |
| Tape | T | Draw copper tape runs |
| Part | P | Place the selected part |
| Move | V | Drag a part, a tape run or a hole |
| Select | S | Pick a part to rename it or give it its own hole and pad size |
| Rotate | — | Click a part to turn it 90° around its first pin |
| Hole | H | Add a mounting screw hole |
| Text | L | Engrave a label into the plate |
| Outline | O | Draw a custom board shape or a cutout |
| Erase | X | Remove anything on the board |

**R** rotates the part under the cursor or the one being placed. Undo and redo are **Ctrl+Z** and **Ctrl+Y**. Scroll to zoom, hold the middle mouse button to pan, and use **Fit** to reset the view. On a phone, pinch to zoom.

### Which side do parts go on?

Footprints are drawn as seen from the tape side. If you push a part's legs in from the plain side and solder on the tape side, chips, modules and connectors come out mirrored — press **⇋ Flip** (or F) for those. Flipped parts show a dashed outline and a ⇋ after their name. Two-leg parts such as resistors don't need it.

---

## Schematic editor

Click **⚡ Draw schematic** in the Auto-generate section. A full-screen drawing area opens.

| Tool | What it does |
| --- | --- |
| Place | Pick a part from the list, tap the grid to put it down. Names like R1 and D1 are assigned for you. |
| Wire | Tap one pin, then another, to join them. |
| Edit | Tap a part to select it, then set its **Value**, **Footprint**, **Rotate**, **Flip** or **Delete**. Drag to move, drag empty space to pan. |
| Delete | Tap a part (its wires go too) or a single wire. |

Every **Ground** symbol is joined to every other, and the same goes for **Power**, so you can drop them wherever you need instead of drawing long wires.

Available symbols: resistor, capacitor (plain and electrolytic), inductor, LED, diode, battery, switch, push button, buzzer, potentiometer, NPN and PNP transistors, N-MOSFET, ground and power, jumper wire, 2 to 8-pin connectors, DIP chips, ESP32, rotary encoder, TP4056 module, and a single pad or test point. Imported KiCad parts appear at the end.

Your drawing is kept on the device, so it is still there next time.

---

## Auto-generate

Describe the circuit as a text list of two kinds of line, then press **Generate layout**.

**Part lines** — a name you choose, a space, then a type:

```
J1 h2
R1 res
D1 led
```

**Connection lines** — a label, a colon, then the pins that join together:

```
VCC: J1.1 R1.1
N1:  R1.2 D1.1
GND: D1.2 J1.2
```

That's a battery, a resistor and an LED in a loop. Lines starting with `#` are notes and are ignored.

Each pin may appear on only one connection line; to join more things to the same point, add them to that line. Pins you leave out stay unconnected, and tape keeps clear of them.

### Part types

| Type | What it is | Pins |
| --- | --- | --- |
| `pad` | A single solder pad or wire point | 1 |
| `res` | Two legs 10.16 mm apart — resistor, diode | 2 |
| `led` | LED, 2.54 mm legs (pin 1 is +, pin 2 is −) | 2 |
| `leg254` `leg508` `leg762` | Two legs 2.54, 5.08 or 7.62 mm apart, such as capacitors | 2 |
| `smd1206` `smd0805` | Surface-mount resistor or capacitor pads, no holes | 2 |
| `sot23` `soic8` | Surface-mount transistor and 8-pin chip | 3 or 8 |
| `h2` `h3` `h4` `h6` `h8` | A single row of 2.54 mm pins — battery connectors, switches, buttons, sensors | 2–8 |
| `dip8` `dip14` `dip16` | DIP chips, rows 7.62 mm apart | 8, 14 or 16 |
| `jmp508` … `jmp2540` | Jumper wire, 5.08 to 25.4 mm (both ends count as joined) | 2 |
| `esp32` `enc` `tp4056` | ESP32 board, rotary encoder, TP4056 charger module | — |

Parts that don't match one of these can still be used: pick the type with the same pin count and spacing, use several `pad` parts, or import a KiCad footprint.

The **Load an example** menu has ready-made boards to read through.

---

## Print settings

| Setting | What it controls |
| --- | --- |
| Plate thickness | Thickness of the printed base |
| Traces | **Raised** lines for tape to sit on, **Lowered** grooves, **Double-sided (two pieces)** (two pieces that are each other's cover, with tape on both faces; tape cannot cross), **Double-sided (strips)** (tape on both faces and it can cross: each tape run is a printed strip held between a bottom cover and a top cover; in both, draw each side with the Top/Bottom switch while the other side shows as a ghost), or **Raised + cover piece** (a base with raised lines plus a cover that drops over the taped traces so they sit below the surface) |
| Cover recess / Cover clearance / Min cover strip | Cover designs (Raised + cover piece and both Double-sided modes): how far the copper sits below the cover top, the gap left around traces and pads so it fits, and the thinnest strip of cover allowed between openings (narrower strips are cut away so nothing is too thin to print) |
| Snap pegs / Snap clips on the edge | Hold the cover (or the other double-sided piece) on without glue. **Round pegs** printed on the base push into round holes through the cover and hold it by a snug fit (**Peg fit**; place them yourself with the **Peg** tool or let the app choose); clips on straight stretches of edge click over the cover (**Clip catch**, cover piece only). Placed automatically in clear spots |
| Pegs for the strips | Double-sided (strips) only: small ears on each strip with a hole that a peg on the other cover goes through, so the strips stay put during assembly. Untick for plain strips |
| Trace height | How far the lines rise or sink |
| Pin hole ⌀ | Size of the through-holes for component legs |
| Larger solder pads | Optional bigger pads, with their own diameter |
| Hole compensation | Added to every hole in the STL, because printers make holes slightly small. 0.2 mm suits most printers. |
| Text size | Size of engraved labels |
| Corner radius | Rounding on a rectangular board |

**Export shape** controls the outline of the plate: the whole board, a rectangle around the design, or **Cut away unused** to save plastic. A custom outline always exports as drawn.

Very thin tape lines are hard to print. Use at least 0.8 mm for a 0.4 mm nozzle.

---

## Files

- **Export STL** — the printable plate (Raised and Lowered).
- **Export base STL / Export cover STL** — the two parts of **Raised + cover piece**.
- **Export top piece STL / Export bottom piece STL** — the two parts of **Double-sided (two pieces)**; the bottom piece is mirrored so it prints traces up.
- **Export bottom cover STL / Export top cover STL / Export strips STL** — the parts of **Double-sided (strips)**; all strips are in one file, top strips on the left and bottom strips (turned over) on the right, so every strip prints copper side up.
- **Download SVG template (1:1)** — a full-size drawing to print on paper and check fit, or cut tape against.
- **Save design / Open design** — a `.json` file holding the board, its connections, imported footprints and your schematic drawing.

---

## Building it

1. Print the plate. A small test board first is a good idea.
2. Press copper tape along the raised lines, running it onto each pad. Trim neatly.
3. Push component legs through the holes and solder them to the tape at each pad.

---

## Changelog

### 1.0.2

The headline of this release is **cover designs**: three new ways to print a board so the copper tape sits below the surface, including two double-sided designs, one of them with tape that can cross. Covers snap on without glue.

**New cover designs**

- **Raised + cover piece.** A new Traces setting that exports two parts: a base with raised lines, so the tape is easy to press on and trim, and a cover with openings shaped like the traces and pads that drops over the taped base, so the copper sits below the surface like a lowered board. **Cover recess** sets how far below, **Cover clearance** sets the gap around the tape, and part names, the LED + and your own text are engraved into the cover. **Export base STL** and **Export cover STL** replace Export STL in this mode.
- **Min cover strip.** Where two openings would leave a strip of cover too thin to print (under 1 mm by default), the strip is cut away and the openings are joined. The base is not changed.
- **Double-sided (two pieces).** Tape on both sides of the board from two printed pieces that are each other's cover: each piece has raised lines for its own side and openings for the other side's tape. Flip the bottom piece onto the top piece and copper shows on both faces. Includes a **Top / Bottom** switch (or press **B**) with the other side shown as a faint ghost so you can line them up; the bottom side is shown turned over (mirrored), as it will really look, a **Swap side** tool, bottom tape drawn in blue, pads split in half when tape reaches them from both sides, a design check for top and bottom tape that overlap, the side of each run in the tape cut list, and **Export top piece STL** / **Export bottom piece STL**. The bottom piece is exported mirrored so it prints with its traces facing up.
- **Double-sided (strips, traces can cross).** Tape on both sides of the board, and top and bottom tape can cross. Each tape run is printed as its own flat strip, held between a bottom cover and a top cover; each cover has windows that show the copper set **Cover recess** below the surface and slots behind them with a lip that holds the strips in. Pads reached from both sides get a full pad on each strip, one above the other, so a leg through them is soldered on both faces. Each strip has one or two small ears beside the tape with a hole in each; a peg on the other cover comes up through it, so the strips cannot slide while the board is put together. The ears are placed automatically and shown on the board, and can be turned off with **Pegs for the strips**. The covers are held together by round pegs. Uses the same Top / Bottom drawing tools as the two-piece mode, plus design checks for runs on the same side too close for their strips and for strips with no room for an ear, the side of each run in the tape cut list, and **Export bottom cover STL**, **Export top cover STL** and **Export strips STL** (bottom strips exported turned over so every strip prints copper side up).

**Added**

- **Snap fit for the cover, no glue needed.**
  - **Round pegs**: solid 3.6 mm posts printed as part of the base (or the lower double-sided piece) that push into round holes through the cover, level with its top, and hold it by a snug fit. **Peg fit** sets the gap around each peg. Push them back out from the top to take the cover off.
  - **Snap clips on the edge**: springy clips cut into straight stretches of the base edge that click over the cover, with **Clip catch** setting how far they reach over.
  - Pegs and clips are placed automatically in clear spots, away from tape, text and holes, and Check design says if they do not fit.
- **Peg tool (G)** to place snap pegs yourself. Move and Erase work on them, they are saved with the design, and Check design warns if one is too close to tape, a hole or text.
- **Pinch to zoom and two-finger panning** on touch screens, in the board view and the 3D preview. One finger still uses the current tool, and starting a pinch never places or draws anything. The 3D preview can also be moved with right-drag or Shift-drag, and resets its view each time it opens.
- The 3D preview shows the base and cover (or the double-sided pieces and strips) either fitted together or laid out as printed, with a **Show apart / Show assembled** button.

**Changed**

- **Trace height** now goes up to 3 mm (was 1 mm).

**Fixed**

- The **Text tool** did nothing in the desktop app (and in embedded previews), because it asked for the words with a browser pop-up those don't support. It now opens its own text box.
- Text could be cut off with the **Fit to used area** and **Cut away unused** export shapes. Automatic part names and the LED + were not counted when sizing the board, Cut away unused ignored text when tracing the outline, and labels that moved after trimming could break the outline into pieces. All text now stays on the plate.
- The toolbar ran off the right edge of the window at 1500 px wide and narrower, hiding Redo and Clear. Keyboard hints now hide below 1640 px and the app name below 1440 px, so it fits down to about 1280 px.

### 1.0.1

**Added**

- **Schematic editor.** Draw the circuit with proper symbols, wire the pins, and build the board from it. Includes part values, a footprint picker, a parts list you can copy, undo and redo, rotate and flip, pinch-to-zoom, and a check that runs before building.
- **Update PCB** keeps your existing layout and only adds, removes and re-links what changed, instead of replacing the board.
- **Check design.** Finds short circuits, copper too close together, tape that is too thin or stops short of a pad, unrouted connections, overlapping parts, copper off the board or in a cutout, and holes cutting into copper. Tap an item to zoom to it. Comes with **Min spacing** and **Min tape width** settings.
- **3D preview** of exactly what the STL will be.
- **Tape cut list** with every run's connection, width, length and bends, plus jumper wire lengths. Copies to the clipboard.
- **Text tool (L)** engraves labels into the plate, with a **Text size** setting. **Engrave part names and LED +** adds them automatically and keeps them clear of tape and pads.
- **Outline tool (O)** draws a custom board shape or a cutout. **Corner radius** rounds a plain rectangle.
- **Flip (F)** mirrors parts whose legs go in from the plain side, so chips, modules and connectors line up. Flipped parts show a dashed outline and a ⇋ after their name.
- **Jumper wires**, both as a part you place and automatically wherever auto-generate needs tape to cross.
- **Redo**, alongside Undo.
- **Dashed connection lines** show which pins still need tape, like a ratsnest, and disappear as you lay it. Hovering a pad names its part, pin and connection, and the design summary counts what is left.
- **Rename parts** from the Select tool.
- **Hole compensation** adds a little to every hole in the STL, because printers make holes slightly small.
- **New part types:** `leg254`, `leg508` and `leg762` two-leg spacings, surface-mount pads `smd1206`, `smd0805`, `sot23` and `soic8`, and jumper wires from `jmp508` to `jmp2540`.
- Parts that come in several sizes are now listed once and ask which size you need.
- Pin 1 of every multi-pin part gets a square pad, which grows to match the tape running onto it.
- A proper app icon and logo.

**Fixed**

- Cancelling a tape run left a ghost of it on the board on phones.
- **Extend** started a new run each time, so corners met as two butted ends instead of a single mitered joint. An extended run is now one piece you can move and reshape as a whole.
- The confirm bar covered the board on phones. It is now a compact row of buttons, and the board is fitted into the space above it.
- The Android app drew underneath the status and navigation bars, hiding the clock and the bottom of the screen.
- The layout ran off the side of the screen on phones.
- Exports (STL, SVG and design files) failed silently in the Android app. They now open the share sheet.
- **Copy** on the tape cut list did nothing where the clipboard was refused.
- The Windows installer and the portable build were written to the same file name, so only one of them survived. They are now `Tape-Board-Setup-…` and `Tape-Board-Portable-…`.

### 1.0.0

First release. Board editor with tape, parts, holes and erase; grid snapping; auto-generate from a text list; KiCad footprint import; per-part hole and pad sizes; STL and SVG export; save and open designs.

---

## Credits

Tape Board was created by **R. Heller**.

If the app is useful to you, you can [buy me a coffee ☕](https://buymeacoffee.com/Rheller82).
