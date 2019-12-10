# Iot-Project
This is documentation for how to configure and install bluetooth and run RFCOMM between raspberry pi's to communicate between a Pi acting as a HUB between two edge devices. One Pi has a sonar sensor that have parameters and sends information to the HUB Pi that then can send information to another Pi that has a stepper motor acting as an actuator. The main HUB Pi communicates betwen a third Pi that is the cloud server that has a web client to access information from the HUB about the Pi's status.

# Devices involved with the project:
HUB Pi communicating with 3 other Pi's. 2 edge devices, and 1 cloud server.

Sensor Pi with Sonar Sensor that sends data to HUB to activate the actuator.

Stepper Motor Pi that activates upon receiving a query from the HUB.

Cloud Server Pi that sends/receives information from HUB Pi and desplays them in a web client that can be accessed by user.

# Getting Started
## Setting Up Bluetooth on the HUB, Sensor Pi, and Stepper Motor Pi
If you have a Raspberry Pi 3B or later, then you should have bluetooth installed. You can check to see what version you have by typing `bluetoothd --version`
The version that we are using is version 5.50 for this project. If you're having issues with getting bluetooth working or don't have bluetooth installed, follow this tutorial on getting started with BlueZ:

https://3pl46c46ctx02p7rzdsvsg21-wpengine.netdna-ssl.com/wp-content/uploads/2019/03/1908_Tutorial-How-to-set-up-BlueZ__UpdateLFC_FINAL.pdf

`sudo apt-get install bluetooth bluez-utils blueman` will also be a good start to what we're going to be using bluetooth for.
