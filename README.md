# Marble_Sorter_V1

This is my latest automation side project: A fully autonomous robot that sorts marbles by color using an ATmega 328p microprocessor.

This project is divided in two parts:

The detection part:
This consists of a 3D printed funnel that leads the mixed marbles to the TCS34725 RGB color sensor which sends color information to the microcontroller.

The sorting part:
This contains a 12VDC Solenoid that pushes marbles into a 3D printed slide that drops into a rotating funnel attached to a mini servo motor controlled by the received color information. The funnel leads the marbles to 6 color-coded 3D printed channels for vertical stacking.

The control of the piston is made using a power MOSFET with the gate connected to a 5V GPIO pin of the microcontroller.
To power up the robot I used an AC-DC converter to provide enough voltage to power up the robot.
All the structure components are designed from scratch in Autodesk Fusion360, and printed on a Bambulab A1 3D printer.

The microcontroller used is an Arduino NANO, but this wasn't my first choice. Firstly I have used an Esp8266 microcontroller which only had 3.3V GPIO pins. That voltage isn't enough to fully open the gate of the MOSFET that I used, so I had to use multiple power transistors to get the Solenoid working. Said and done; with another bipolar transistor used, the system worked as intended, but the electronic circuit took to much space, and I did not like that. Lastly I've decided to use the Arduino NANO microcontroller because of its 5V GPIO pins. That reduced the number of transistors used, and the space needed for the circuit.

One of the most important tasks was the color sensor calibration. The color information also depended on the ambient light of the room, so I needed to enclose the detection part of the system, so no light reaches the color sensor. Then I just had to find the perfect fit between the color parameters of the sensor and the real color of the marble.
