# Iot-Project
This is documentation for how to configure and install bluetooth and run RFCOMM between raspberry pi's to communicate between a Pi acting as a HUB between two edge devices. One Pi has a sonar sensor that have parameters and sends information to the HUB Pi that then can send information to another Pi that has a stepper motor acting as an actuator. The main HUB Pi communicates betwen a third Pi that is the cloud server that has a web client to access information from the HUB about the Pi's status.

# Devices involved with the project:
HUB Pi communicating with 3 other Pi's. 2 edge devices, and 1 cloud server.

Sensor Pi with Sonar Sensor that sends data to HUB to activate the actuator.

Stepper Motor Pi that activates upon receiving a query from the HUB.

Cloud Server Pi that sends/receives information from HUB Pi and desplays them in a web client that can be accessed by user.

# Getting Started
