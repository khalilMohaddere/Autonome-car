# Autonome-car
A simulator/client/server that features autonomous localization (using a 'particle filter') and distant control of an arduino/raspberry pi powered car.


<img width="1279" height="781" alt="image" src="https://github.com/user-attachments/assets/28a518f6-d7b5-4e2d-8edc-10d5eb84de59" />

For the (real) car, an arduino (for motor control and sensor readings) and a raspberry pi (for communication) are used. You can the robot's arduino sketch, autonomee.ino, car.h and compass.h.
# Features
<img width="1118" height="466" alt="image" src="https://github.com/user-attachments/assets/14d9f554-cee8-42a1-9490-3536050de1fc" />
A basic SVG parser
A pathfinder (A*)
Nearest obstacle detection (to simulate the sensor's measurements)
Basic probability model : particle filter. (hopefully we'll also implement one based on Kalman's filter)
Visualization of the robot's movements and the particles used to localize it.
A client/server to push commands to the car and control it (through serial ports)

# Dependencies
Python 2.7
Qt and PySide (Qt's python binding)
Numpy
PySerial
Scipy

# Communication Protocole 
The packets sent to the server (TCP) respect this format:

OPCODE(2 chars) + "#" + OPERANDE 1 (6 chars) + "#" + OPERANDE 2 (6 chars)

# Supported Opérations

Running forward: OPCODE=01 ; Example : 01#000000#000000

Running backward: OPCODE=-1; Example : -1#000000#000000

Turning right : OPCODE=02 ; Example : 02#000000#000000

Turning left : OPCODE=-2 ; Example : -2#000000#000000

Setting speed : OPCODE=05, first operand is a factor ranging from 0 to 250. ; Example : 05#000180#000000

# Mobile App

A (responsive) mobile (Android) client compatible with the communication protocol used has been developped by Alexis Fasquel.

<img width="1277" height="710" alt="image" src="https://github.com/user-attachments/assets/1065f804-6294-44bd-84b5-e4b407c89483" />

<img width="360" height="600" alt="image" src="https://github.com/user-attachments/assets/a9fe19d2-ee7c-493b-a0df-0a707ad14e06" />



