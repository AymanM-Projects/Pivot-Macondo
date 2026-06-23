# Pivot-Macondo

What I created is a motorized mount that holds my friend's camera on a tripod so a person standing far away can point it, zoom it, and hit record all wirelessly from a controller, without ever touching the camera.

The reason I actually started this project is that I really wanted to create something with new CAD and coding skulls and really start using these skills to create  something meaningful, but  why I decided to create this mount specifically is for my childhood friend. I've known him for ten years. He's grown this passion for  cameras, photography, and videography, and I have noticed how he has enjoyed it when he does it. He uses cameras to make stories, to help people, we do advocacy. I thought it would be amazing for me and him to combine our talents and our passions, because I want to do the same thing.

What really matters to me is that I can actually use what I'm good at to create something with strength behind it. I want to create, I love making things, not just for myself, and not for money, but things that actually matter to people and make a real difference in their lives. I don't want anything in return for this. I just want to see people happy.

And I don't want this to be the end, I want it to be the start. Creativity can go a lot of ways. For me it's coding and hardware. But not just making things,  making new inventions. Creating products. Not just products, but inventions and innovations that change people's lives. That's why I'm starting here, with something I have a real passion to work on. I saw this kind of technology  and I knew I could make it the moment I saw it.


For the actual technical components I used **Onshape** for modeling and my **Bambu P2S** for test prints.


The mount contains 3 main components:
1. A Panning mechanism powered by a nema 17 stepper motor that is at the bottom and will rotate the hole mount 360 degrees 
2. A tilting mechanism that uses another nema 17 but also a bearing and a metal rod that goes through the drive and idle arms, it should rotate the entire camera cage 90 degrees vertically.
3. Lastly a zoom feature that works with a Pinion Motor gear  and a focus ring and a 28BYJ-48  for zooming the camera


Some additional things:
-  Through this project I learned a lot about clearance and how 3dc printing warps holes Before I thought you could design with exact parameters for each design but now i realize that you need to add clearance values for certain structures/features
- I learned what a driver is and how it works with a stepper motor
- I learned how to do torque math, for my two spinning motors(pan/tilt)

Things I want to do in the future:
- Right now It only fits my friends camera and fits for his tripod but i want to make it so it is like a phone holder and you can basically connect it to any camera through a slider or springs
- I want to add a way for users to make it go horizontal and vertical on a slider with a another motor because i feel this can be more useful
- I want to try using more gears or getting the price down for future builds
- 
## BOM

| Subsystem | Item | Purpose | Price | Source |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| Pan mechanism | Lazy Susan Bearing 4 inch | Carries the rotating pan load (bearing takes the weight, not the motor shaft) | $4.99 | [Amazon](https://www.amazon.com/Turntable-Bearing-Rotating-Cabinet-Profile/dp/B09V2S71J1) |
| Pan mechanism | TMC2209 V1.3 Stepper Motor Driver (6-pack) | Drives a stepper motor quietly with current control | $29.99 | [Amazon](https://www.amazon.com/BIGTREETECH-Direct-TMC2209-Stepper-Control/dp/B08WZFK9KT) |
| Pan mechanism | NEMA 17 Stepper Motor (MAKERELE, 42-40mm) | Direct-drive pan axis rotation | $12.99 | [Amazon](https://www.amazon.com/MAKERELE-Stepper-42-48mm-Connector-Printers/dp/B0FP1QQ1NT) |
| Tilt mechanism | NEMA 17 Stepper Motor L=39mm 10:1 Planetary Gearbox | Geared tilt axis drive (holds the camera against gravity) | $37.99 | [Amazon](https://www.amazon.com/STEPPERONLINE-Nema-Stepper-Motor-Ratio/dp/B0F4CKD1VC) |
| Tilt mechanism | 608ZZ Ball Bearing (10 pcs) | Supports the tilt pivot shaft | $4.87 | [Amazon](https://www.amazon.com/Bearings-Double-Shielded-Miniature-Skateboard/dp/B07H83VV6B) |
| Tilt mechanism | 8mm dia 300mm 304 SS Round Rod (2 pcs) | Tilt pivot shaft + zoom support rod (cut to length) | $11.99 | [Amazon](https://www.amazon.com/Etauwe-Diameter-Length-Stainless-Working/dp/B0G78Y8HB4) |
| Tilt mechanism | 8mm Shaft Lock Collar (10 pcs) | Locks shafts axially in place | $8.89 | [Amazon](https://www.amazon.com/Zeberoxyz-Stainless-Material-Isolation-Accessories/dp/B08SK2LNNV) |
| Zoom mechanism | M3 M4 M5 Screws & Nuts Assortment Kit (460 pcs) | General fasteners across all assemblies | $13.49 | [Amazon](https://www.amazon.com/Hilitchi-510pcs-Stainless-Socket-Assortment/dp/B06XRFKNPQ) |
| Zoom mechanism | 0.8M 5mm Pinion Motor Gear 11T (3 pcs) | Steel pinion meshes with the lens gear ring to drive zoom | $9.99 | [Amazon](https://www.amazon.com/Fraizoe-RC-0-8M-5mm-3Pcs/dp/B0DYK2Z85B) |
| Zoom mechanism | 28BYJ-48 ULN2003 5V Stepper Motor (5 sets) | Drives the zoom ring with repeatable position | $14.99 | [Amazon](https://www.amazon.com/ELEGOO-28BYJ-48-ULN2003-Stepper-Arduino/dp/B01CP18J4A) |
| Zoom mechanism | SmallRig Seamless Gear Ring (72mm–74mm) | Rubber gear ring grips lens zoom barrel (removable, no marring) | $2.99 | [Amazon](https://www.amazon.com/SmallRig-Seamless-Focus-Gear-Ring/dp/B0986XSTP4) |
| Battery/wiring | AITRIP ESP32 30-pin USB-C (3-pack + expansion boards) | Microcontrollers for mount + controller (ESP-NOW link) | $9.99 | [Amazon](https://www.amazon.com/dp/B0B82CKB1K) |
| Battery/wiring | Anker Nano Power Bank 10000mAh 30W | Portable power source for the mount | $49.99 | [Amazon](https://www.amazon.com/Anker-Portable-Charger-Compatible-MacBook/dp/B0C9CJKCH3) |
| Battery/wiring | ACEIRMC ZY12PDN PD Trigger (2-pack screw terminals) | Pulls fixed 12V from the bank for the stepper rail | $14.99 | [Amazon](https://www.amazon.com/dp/B0CNVQMP6C) |
| Prototyping | ELEGOO 830-Point Solderless Breadboard (3 pcs) | Solderless prototyping of control/trigger circuits | $8.99 | [Amazon](https://www.amazon.com/EL-CP-003-Breadboard-Solderless-Distribution-Connecting/dp/B01EV6LJ7G) |
| Prototyping | ELEGOO 120pc Dupont Jumper Wires (M/M + M/F + F/F) | Breadboard interconnects in all three pin genders | $6.98 | [Amazon](https://www.amazon.com/Elegoo-EL-CP-004-Multicolored-Breadboard-arduino/dp/B01EV70C78) |
| Camera trigger | NOYITO PC817 1-Channel Optocoupler Module (screw terminals; 2-pack) | Isolated shutter signal, no electrical connection to the borrowed camera | $6.99 | [Amazon](https://www.amazon.com/NOYITO-1-Channel-Optocoupler-Optoelectronic-Anti-Interference/dp/B0B537T73S) |
| Camera trigger | CablesOnline 2.5mm TRS Male to 3-Pole Screw Terminal Connector (5-pack) | Plugs into S5ii remote port for shutter/record (verify pinout before wiring) | $16.95 | [Amazon](https://www.amazon.com/CablesOnline-3-Screw-Terminal-Connectors-PL-CN22-5/dp/B01J4JLP6K) |
| Power/filtering | ALLECIN 24-Value Electrolytic Capacitor Assortment Kit | Incl. 100uF/220uF/470uF — one cap across each driver VM absorbs spikes | $9.99 | [Amazon](https://www.amazon.com/ALLECIN-Electrolytic-Capacitor-Assortment-Kit/dp/B0C1VBXCQM) |
| Control input | 8BitDo SN30 Pro Bluetooth Gamepad | Bluepad32-compatible name-brand controller for the gamepad path | $44.99 | [Amazon](https://www.amazon.com/Bluetooth-Controller-Compatible-Raspberry-Gaming-Console/dp/B0CSP6TTJJ) |
| Filament | Black PETG Filament (1kg spool) | Structural printed parts (brackets, cradle, column) | $19.00 | [Bambu Lab](https://us.store.bambulab.com/products/petg-hf) |
| Tools | Onshape | CAD modeling | Owned (free) | |
| Tools | Bambu P2S 3D Printer | Manufactures the printed parts | Owned | |
| Tools | Arca Quick-Release Clamp | Tripod connection (already owned) | Owned | |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| | | | | **Total: $342.03** |





# CAD
### Individual Parts:
quick release clamp(for connecting to the camera cage)
<img width="683" height="463" alt="image" src="https://github.com/user-attachments/assets/cfe6f1e7-7fcd-44c2-ac00-9c3ee46e0fb0" />
<img width="623" height="518" alt="image" src="https://github.com/user-attachments/assets/36d3f0a1-d75a-4299-b57f-7c83fb97eb74" />

panning mechnism(connects to tripod and holds motor)
<img width="793" height="606" alt="image" src="https://github.com/user-attachments/assets/99deec8b-7953-489d-927b-74dc1de33e93" />
<img width="829" height="355" alt="image" src="https://github.com/user-attachments/assets/4b03892a-5c51-47c2-a2d5-7d504ac19011" />

holder for camera cage w motor box for tilt motor
<img width="722" height="425" alt="image" src="https://github.com/user-attachments/assets/c55408dd-d9ff-40dd-997a-20a5af73989d" />

zoom(holder for the zoom motor and pinion gear to connect to the rest of the mount)

<img width="372" height="479" alt="image" src="https://github.com/user-attachments/assets/daa2c252-af93-4112-9057-d46c8aa09137" />


### Assembly 

<img width="968" height="923" alt="image" src="https://github.com/user-attachments/assets/eee50a84-b2af-4d06-9cce-fec3edd7a6de" />





Refrence(inspiration):https://github.com/geg-tech/biblicallyaccuratekeyboard/blob/main/README.md - I liked the format and the friendly tone, 
