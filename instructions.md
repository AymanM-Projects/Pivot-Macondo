# Pivot — Build & Assembly Instructions

Pivot is a wireless motorized PTZ mount for a Panasonic Lumix S5II + Lumix S 20-60mm lens (1,090 g payload). It does pan, tilt, zoom-ring drive, and photo/record trigger, controlled over ESP-NOW from a second ESP32 up to ~50 m away. Everything structural is 3D printed in PETG. This doc should let anyone reproduce the build.

> Items marked **[VERIFY]** need to be confirmed against the physical build before following blindly. Items marked **[FILL IN]** are placeholders I still need to complete.

---

## 1. What you need

### Tools
- 3D printer (built on a Bambu Lab P2S, any printer with a ~256 mm bed works) + PETG filament
- Soldering iron, solder, heat shrink
- Metric hex keys, small screwdrivers
- Multimeter (required — you verify voltages before connecting anything to the camera side)

### Parts
Full parts list with links and prices is in [`BOM.csv`](./BOM.csv). Summary:

| Subsystem | Part |
|---|---|
| Pan motor | NEMA 17 stepper |
| Tilt motor | NEMA 17 stepper with 10:1 planetary gearbox |
| Stepper drivers | TMC2209 **[VERIFY — reconcile with A4988 in older diagrams]** |
| Zoom motor | 28BYJ-48 stepper + ULN2003 driver board |
| Zoom gear | SmallRig 3293 rubber gear ring (0.8 MOD, fits Ø72–74 mm lens) + steel 0.8M 19T pinion, 5 mm bore |
| MCU ×2 | 30-pin USB-C ESP-WROOM-32 dev boards (one on mount, one in controller) |
| Shutter trigger | PC817 optocoupler module + 2.5 mm TRS male-to-screw-terminal connector |
| Power | Anker Nano 30W 10,000 mAh USB-C PD bank + ZY12PDN PD trigger set to 12 V |
| Bearing | Lazy Susan bearing (pan base) |

**Do not substitute the 2.5 mm TRS connector with a 3.5 mm or 4-pole part** — it will not fit the S5II remote port.

---

## 2. Print the parts

All custom parts are STEP files in [`My_parts/`](./My_parts/). Imported models (with credits) are listed in [`Imports/intro.md`](./Imports/intro.md).

- Material: PETG for everything structural
- Layer height / infill / orientation per part: **[FILL IN — table of each part with print settings and orientation]**
- Parts use triangular truss pocketing printed flat-side-down, apex-up
- The electronics box has no pocketing on purpose (keeps debris out) — print it as modeled

---

## 3. Mechanical assembly

### 3.1 Pan base
1. Bolt the lazy Susan bearing between the tripod base plate and the pan platform. **[VERIFY bolt sizes]**
2. Mount the pan NEMA 17 in the column. **[FILL IN — how the motor drives the platform: direct/geared, and fastener details]**
3. The base mounts to any standard tripod via the 1/4"-20 thread.

### 3.2 Tilt yoke
1. Assemble the yoke arms onto the pan platform.
2. Mount the tilt NEMA 17 + planetary gearbox on the drive side.
3. Set the camera cradle so the tilt pivot passes through the camera's center of gravity — this is what keeps holding torque low. **[FILL IN — CG reference measurement for S5II + 20-60mm]**
4. Sweep tilt ±45° by hand and check nothing collides before wiring the motor. **[VERIFY — interference sweep and Ø9 vs Ø11 through-hole on drive side]**

### 3.3 Zoom drive
1. Wrap the SmallRig 3293 gear ring around the lens zoom ring. Friction fit only — nothing adhesive ever touches the lens.
2. Measure the installed ring OD before trusting the bracket spacing (center distance is ~46.8 mm provisional).
3. Fix the 19T steel pinion on the 28BYJ-48 shaft (set screw on the flat).
4. Mount the zoom bracket and use the vertical slots (±1.5 mm) to set gear mesh: snug, no binding, no skipping. The rubber ring slipping under overload is intentional — it's the torque fuse.

### 3.4 Camera
Camera mounts by its 1/4"-20 socket into the cradle. **[FILL IN — cage/cradle attachment details]** No clamps or adhesives on the camera or lens; everything must come off without a mark.

---

## 4. Electronics

The full schematic is in the repo (EasyEDA export). **[FILL IN — link the exact file]**

### 4.1 Power
- USB-C PD port → ZY12PDN trigger fixed at **12 V** → stepper motor rail
- USB-A port → **5 V** → ESP32 and logic
- All grounds common
- Budget: ~19 W peak, ~8.5 W average, ~3 h runtime on the 10,000 mAh bank
- Never wire a motor directly to an ESP32 pin — everything goes through its driver

### 4.2 Wiring table
**[FILL IN — pin-by-pin table from the EasyEDA schematic: driver STEP/DIR/EN pins, ULN2003 IN1-4, optocoupler input, with ESP32 GPIO numbers]**

### 4.3 Camera trigger — read this before connecting anything
The S5II remote port is **not** a simple switch closure. It expects ~2 kΩ across the line for shutter and ~5 kΩ for focus. The PC817 optocoupler module isolates the camera from the ESP32; its VCC pin is left unconnected on purpose. **[VERIFY resistor values against a trusted Panasonic pinout source before first connection — wrong wiring can damage the camera.]** Test the trigger circuit with a multimeter before the 2.5 mm plug ever goes into the camera.

---

## 5. Firmware

- Platform: Arduino IDE, ESP32 board package, plain Arduino C++
- Two sketches: mount side and controller side, linked by ESP-NOW (peer-to-peer, no router)
- Flash each board over USB-C. **[FILL IN — board selection settings, MAC address pairing steps]**
- Position tracking is step-counted with firmware soft limits (no hard stops on the zoom ring)
- On startup the zoom axis runs a homing routine. **[FILL IN — homing procedure]**

---

## 6. First power-up checklist

1. Power the mount with **no camera installed**.
2. Verify 12 V on the stepper rail and 5 V on logic with a multimeter.
3. Test each axis individually from the controller: pan, tilt, zoom.
4. Verify trigger output resistance with a multimeter.
5. Only then install the camera and connect the 2.5 mm plug.

---

## 7. Troubleshooting

| Symptom | Check |
|---|---|
| Steppers hum but don't turn | Driver current setting, STEP/DIR wiring swapped |
| Zoom ring skips | Gear mesh too loose — adjust bracket slots |
| Zoom ring stalls lens | Mesh too tight, or hitting soft limit |
| No wireless link | ESP-NOW MAC addresses paired correctly, both boards powered |
| Camera won't trigger | Resistor values, TRS plug fully seated, correct 2.5 mm 3-pole part |
