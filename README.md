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


BOM

Subsystem
Name/Part
Purpose
Qty
Price (USD)
Source/Link
Pan mechanism
Lazy Susan bearing 4 inch
Carries the rotating pan load (bearing takes weight not motor shaft)
1
5
https://www.amazon.com/Turntable-Bearing-Rotating-Cabinet-Profile/dp/B09V2S71J1/ref=sr_1_1_sspa?crid=1G30ZM5ENCA9A&dib=eyJ2IjoiMSJ9.NFJ-X99JMNrmoyST0lSXXqBl3Zx-osiU8x_6G42GzXEUXGsRGhfgkDl0KK69LsWHaEblw6zJDKVoPSo7ncpJrmWocYXQqt5cVKKEmxTNx2dX47QZAE3gvixmSC38XliIaCGyZucsEnGcs8R6nrjtll88xaC6NT2jeKCBpcI2ak1gBCMt2FXRzSXZIDpNZA_XFfoZTH8kyhjTNGpSOpBvkj0qCTlwI53GnMi7ZS3oBQwC5xniTB_ry5pcHdvjqQ6aNsqDaRlMFhq58AC-U625B9X3jly3dVUjwzI6g6wlXBo.DUQlEi5Jt7ViYSWLahHTDvFBgNrIQfQaj59Swls4J-E&dib_tag=se&keywords=lazy+susan+bearing+4+inch&qid=1780185850&sprefix=azy+susan+bearing+4+inch%2Caps%2C135&sr=8-1-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&psc=1
Pan mechanism
TMC2209 V1.3 Stepper Motor Driver
Drives a stepper motor quietly with current control
1
30
https://www.amazon.com/BIGTREETECH-Direct-TMC2209-Stepper-Control/dp/B08WZFK9KT/ref=sr_1_2_sspa?crid=3U7CS0N3XHD66&dib=eyJ2IjoiMSJ9.aIayFIoQu1uXR8DjH6-HCTpCcacoMEmXXodGg4jOBzxlLiVqNnQ_7uFf1iSyrhB9JjGy_KSJXhPqvgD9cJkCEuAuPeLBPpOUQXSWYGn35psLw1HLNsxfr9Gq7pN9b3UURtM1sfYLO-afYx7SsTpwjaCrRzpQReIXZPBkgZdetw6rOP6bUMq05b6Tdl-HFnoa331lNtgGSbySk_OQOIz9PRqCYD4F7ymeQ9TDsYwZgrk.UrtLVX-Wg0vgxiQfk1S_N6pqaNZZ2khxHiIoTK9UaN4&dib_tag=se&keywords=TMC2208%2Bstepper%2Bdriver&qid=1780185851&sprefix=tmc2208%2Bstepper%2Bdriver%2Caps%2C148&sr=8-2-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&th=1
Pan mechanism
Nema 17 Stepper Motor
Direct-drive pan axis rotation
1
13
https://www.amazon.com/MAKERELE-Stepper-42-48mm-Connector-Printers/dp/B0FP1QQ1NT/ref=sr_1_3?crid=ZZIIGBQ0ITS3&dib=eyJ2IjoiMSJ9.5gA4cxErQWveU5HN8z4zl9nLMbvTHDC-VXOGxoeyY6Ud5FNLFPmp3dzYoiYKexR-l2RypqjzAapydfaM6b1nN0aC2b6C-VitvXkFBF7k9gTJA8zqF7QV9HLo4APyLoo4Jtslu95G-2eU9nVtXfBuj6saFSbAmrq1LMUY8AJAeiv_69gWuYxhMsPDKIWTMSOa3zeTUdm19dGo1IASU3EaAIqoqA4r-capHaHkk4oSWYg.hQ3uH3AvH9hg6bss627IoC_l0YhEDyTi6XqivX8gwUc&dib_tag=se&keywords=nema%2B17%2Bstepper%2Bmotor%2B51Ncm&qid=1780185791&sprefix=nema%2B17%2Bstepper%2Bmotor%2B51ncm%2Caps%2C121&sr=8-3&th=1
Tilt mechanism
Nema 17 Stepper Motor L=39mm 10:1 30arcmin MG Planetary Gearbox
Geared tilt axis drive (holds camera against gravity)
1
37
https://www.amazon.com/STEPPERONLINE-Nema-Stepper-Motor-Ratio/dp/B0F4CKD1VC/ref=sr_1_1?crid=FN6U5YIQK1U6&dib=eyJ2IjoiMSJ9.dD4m3VMvwS56mCCoc4dUpokUKAoz1RWux137zjvJdakRYckrmdV67BwkzoD5xO9ZSKL_Rg8ObNFC6TwSKaEV7oR6wRJTTnDVljICT4345E78Fnc7k_rPmnIhbSWVY9qmLvTuJe2f7psSiEI5WR21erqXievhOuU6L-xqVhyaDJM9_HIfO75uJ6KuuUDiUV27WXSEGMPvfxsDc1ilIE1jdGa-5zuDLK-5biOxw798bcY.MwiHqK-tu6qUnCKsXmRy2U_CbR4TbyiTdwS5bWQSKLw&dib_tag=se&keywords=Nema+17+Stepper+Motor+L%3D39mm+Gear+Ratio+10%3A1+MG+Series+Planetary+Gearbox&nsdOptOutParam=true&qid=1780620846&sprefix=nema+17+stepper+motor+l+39mm+gear+ratio+10+1+mg+series+planetary+gearbox%2Caps%2C150&sr=8-1
Tilt mechanism
608 ZZ Ball bearing (10 pcs)
Supports the tilt pivot shaft
1
4
https://www.amazon.com/Bearings-Double-Shielded-Miniature-Skateboard/dp/B07H83VV6B/ref=sr_1_3?crid=1W3RQA68JNSRG&dib=eyJ2IjoiMSJ9.uvdKMqgDBQdb8G2PMx6S78L8Uef1rXBTXHzqnEHrVKLSFKvB0BwDj3T_oFZTHsCLpV8Ji0VTYM7gqp828nRDFD2TNu5MRr3I6HqF8bEAGo9neHtihaaDvyW7xb23Co1YNx_lZcOP59Rr255I_Nq5yU09neWfv015rgp4_apSZH7Yehp7qhqZV-9NXkoYOV-_sN3_9HZ1jwdiHOALF8jiW6gbNarbpkKtke8nXxYVcc0.GI2XLOx5wkbnQW9YWRZ_8bttuzB3kd12puzA63_d2nQ&dib_tag=se&keywords=608zz+bearings&qid=1780621126&sprefix=608ZZ+bearing%2Caps%2C240&sr=8-3
Tilt mechanism
8mm dia 300mm 304 SS Solid Round Rod (2 pcs)
Tilt pivot shaft + zoom support rod (cut to length)
1
12
https://www.amazon.com/Etauwe-Diameter-Length-Stainless-Working/dp/B0G78Y8HB4/ref=sr_1_1_sspa?crid=2EG99GGFYZY7M&dib=eyJ2IjoiMSJ9.uSOA0Si67bIKJf3YFlVvqGGX8nn21KCL5JiaTJfJBWRdoD48QGBFzGZ8fq3FsGylvf-hFXqUxWNdstO79Umz0pHpXbaXksHMgzyI4CZuJIG7si0_1I0A9UgXOHVhvoTcaIZq10Baw18mUKi42HxeX836F3tFh-wa1P_XdlpAzvEoGDD60gOTpAtY309UIuXIDR-F1G9Ja5rI4TvfoHJgAGdh1eDm-eha7A2FzrlC-Hk.9ILu5Vj5I_sh9UoaACrZbVUhVjqBmll7FarUN5RXxzY&dib_tag=se&keywords=8mm%2Bsteel%2Brod%2B120mm&qid=1780621343&sprefix=8mm%2Bsteel%2Brod%2B120mm%2Caps%2C139&sr=8-1-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&th=1
Tilt mechanism
8mm Shaft Lock Collar (10 pcs)
Locks shafts axially in place
1
9
https://www.amazon.com/Zeberoxyz-Stainless-Material-Isolation-Accessories/dp/B08SK2LNNV/ref=sr_1_3?crid=2L5HRRB0G29FP&dib=eyJ2IjoiMSJ9.VoVHEboZNUOsR_2DNwUaikgevHzFm4sN1uXWRRJgkv6Bm_ugERYgZ9frMvTLI6GqOCuMOyS1uUG4kYDH2d_n4k73lyeoVADv8oUH6Mk5blDVq8kkgOdlqq_ZpkQ6YxbZHAZSVbDXyeAn5Qb8PUT_tATqEZhok5O6HngthHsah8q9FQakCnH-tUia1_fjaTc-yj9_WDqoq8tGEXMyw9lgJUV2vFLskUpBU7EbrT5Tazs.Kb-8ALiz6CQEIvkddLTmDv_Pha2YNJelzzRP07cmlqk&dib_tag=se&keywords=8mm%2Bshaft%2Bcollar&qid=1780621555&sprefix=8mm%2Bshaft%2Bcollar%2Caps%2C382&sr=8-3&th=1
Zoom mechanism
M3 M4 M5 Screws Nuts Assortment Kit
General fasteners across all assemblies
1
15
https://www.amazon.com/Hilitchi-510pcs-Stainless-Socket-Assortment/dp/B06XRFKNPQ
Zoom mechanism
0.8M 5mm Pinion Motor Gear (3 pcs)
Steel pinion meshes with the lens gear ring to drive zoom
1
10
https://www.amazon.com/Fraizoe-RC-0-8M-5mm-3Pcs/dp/B0DYK2Z85B
Zoom mechanism
28BYJ-48 ULN2003 5V Stepper Motor (5 pcs)
Drives the zoom ring with repeatable position
1
15
https://www.amazon.com/ELEGOO-28BYJ-48-ULN2003-Stepper-Arduino/dp/B01CP18J4A
Zoom mechanism
SmallRig Seamless Focus Gear Ring (72mm to 74mm)
Rubber gear ring grips lens zoom barrel (removable no marring)
1
3
https://www.amazon.com/SmallRig-Seamless-Focus-Gear-Ring/dp/B0986XSTP4
Battery/wiring
AITRIP ESP32 30-pin USB-C (3-pack + expansion boards)
Microcontrollers for mount + controller (ESP-NOW link)
1
20
amazon.com/dp/B0B82CKB1K
Battery/wiring
Anker Nano Power Bank 10000mAh 30W
Portable power source for the mount
1
30
https://www.amazon.com/Anker-Portable-Charger-Compatible-MacBook/dp/B0C9CJKCH3/ref=sr_1_5?crid=1QJ7DSWT1XHYK&dib=eyJ2IjoiMSJ9.LdS4JcWDalsmyIEtOTj4vfQmMGDxWZPlwINEJEdQHLr1TYl52ESpWyeo0X0EBa4Jrug2bMBUlTSU0sCYjzZDqRHcEW2yxoDi-FO3skj1alQPN__CeB2GF0yYFn366Kf2qBaU-6_E3tK7QhYfN4d3sBytVkW4PnETp3eOdRSOyxlTyAVfP1bnw0rPYGP6JLeRXX6_0SAbPNRcuIUaXB9ZRDVQbS3KyFqre9njstQWJhw.Mj2Q9zyjoxB94HFLgEfnxul54ruyBRSUTEkyI_kB3co&dib_tag=se&keywords=Anker%2BNano%2BPower%2BBank&qid=1781061271&sprefix=nema%2B17%2Bstepper%2Bmotor%2B51ncm%2Caps%2C90&sr=8-5&th=1
Battery/wiring
ACEIRMC ZY12PDN PD trigger (2-pack screw terminals)
Pulls fixed 12V from the bank for the stepper rail
1
10
amazon.com/dp/B0CNVQMP6C
Filament
Black PETG filament (1kg spool)
Structural printed parts (brackets cradle column)
1
18–20
https://us.store.bambulab.com/products/petg-hf
Total






233
















CAD( I used onshape)
individual parts:


assembly 

Refrence(inspiration):https://github.com/geg-tech/biblicallyaccuratekeyboard/blob/main/README.md - I liked the format and the friendly tone, 
