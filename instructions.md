# Pivot — Build & Assembly Instructions

Hi guys here are general assembly instructions but also linked below is a assembly timelapse (pictures included) in assembly instruction

---

## 1. What you need/materials

### Tools
- 3D printer (I printed with a Bambulab 2 and engineering plate) + PETG filament (any color works, I also specified where you can use PLA and the cost of each print plate)
- Soldering iron, solder, heat shrink
- Metric hex keys, small screwdrivers
- Multimeter
- all the parts listed in the BOM, listed below

---

## 2. Print the parts

All custom parts are STEP files in [`My_parts/`](./My_parts/). Imported models (with credits) are listed in [`Imports/intro.md`](./Imports/intro.md).

- Material: PETG for everything structural/PLA when specified
- Layer height / infill / orientation per part: **[FILL IN — table of each part with print settings and orientation]**
- Parts use triangular truss pocketing printed flat-side-down, apex-up
- The electronics box has no pocketing on purpose

Print pics: one of each build plate with Bambulab settings :

1.
2.
3.
4.
5.
etc

---

## 3. Mechanical assembly :after you finished prints and they look liek pics/also pictures willbe provided for every part of the process once built.

### 3.1 Pan base
1. Bolt the lazy Susan bearing between the tripod base plate and the pan platform. ""need to add bolt sizes"
2. Mount the pan NEMA 17 in the column. **havent fully finished the fastener**
3. The base mounts to any standard tripod via the 1/4"-20 thread.

### 3.2 Tilt yoke
1. Assemble the yoke arms onto the pan platform.
2. Mount the tilt NEMA 17 + planetary gearbox on the drive side.
3. Set the camera cradle so the tilt pivot passes through the camera's center of gravity. 
4. Sweep tilt ±45° by hand and check nothing collides before wiring the motor. **this is just for testing**

### 3.3 Zoom drive
1. Wrap the SmallRig 3293 gear ring around the lens zoom ring. Friction fit only.
2. Measure the installed ring OD before trusting the bracket spacing (center distance is ~46.8 mm provisional).
3. Fix the 19T steel pinion on the 28BYJ-48 shaft (set screw on the flat).
4. Mount the zoom bracket and use the vertical slots (±1.5 mm) to set gear mesh: snug, no binding, no skipping. The rubber ring slipping under overload is intentional — it's the torque fuse.

### 3.4 Camera
Camera mounts by its 1/4"-20 socket into the cradle. **[FILL IN — cage/cradle attachment details]** No clamps or adhesives on the camera or lens; everything must come off without a mark.

---

## 4. Electronics

The full schematic is in the repo (EasyEDA export). **its in electronics folder in the repo**

### 4.1 Power
- USB-C PD port → ZY12PDN trigger fixed at **12 V** → stepper motor rail
- USB-A port → **5 V** → ESP32 and logic
- All grounds common
- Budget: ~19 W peak, ~8.5 W average, ~3 h runtime on the 10,000 mAh bank
- Never wire a motor directly to an ESP32 pin — everything goes through its driver

### 4.2 Wiring table
The wiring diagram is here(also located in electronics/wiringdiagram.md):<img width="1022" height="422" alt="image" src="https://github.com/user-attachments/assets/0c20d363-3829-49d7-9f1d-b29f9dbdedfd" />


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
