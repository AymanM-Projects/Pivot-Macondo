Here is my wiring diagram that I made in EasyEDA. The ESP32 sits in the center and acts as the brain of the whole thing. It connects out to the motor drivers and the camera, so every axis and the shutter all run off this one board.

For pan and tilt, the ESP32 drives two stepper drivers, and each driver runs its own NEMA-17 motor. The driver sits between the ESP32 and the motor because the ESP32 pins can only push a tiny bit of current, nowhere near enough to move a stepper, so the driver does the heavy lifting and the ESP32 just tells it when to step and which direction.

The zoom uses a different driver-motor module (the 28BYJ-48 with its ULN2003 board) since it's a smaller geared motor and doesn't need the bigger stepper drivers the pan and tilt use.

The shutter trigger goes through an optocoupler so the camera stays electrically isolated from the rest of the build. The ESP32 signal pin lights the LED side of the optocoupler, and the output side closes the connection to the camera's 2.5mm port through a 2kΩ resistor, which is the value Panasonic needs to register a shutter press.
<img width="1302" height="534" alt="image" src="https://github.com/user-attachments/assets/75073fae-ca4b-4b09-8a00-34638d792462" />
Full wiring diagram from EasyEDA. ESP32 in the center driving pan and tilt (NEMA-17 steppers via their drivers), the zoom motor through its own driver module, and the camera shutter through an isolated optocoupler.
