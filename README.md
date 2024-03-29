# Iot-Project
This is documentation for how to configure and install bluetooth and run RFCOMM between raspberry pi's to communicate between a Pi acting as a HUB between two edge devices. One Pi has a sonar sensor that have parameters and sends information to the HUB Pi that then can send information to another Pi that has a stepper motor acting as an actuator. The main HUB Pi communicates betwen a third Pi that is the cloud server that has a web client to access information from the HUB about the Pi's status.

# Devices involved with the project:
HUB Pi communicating with 3 other Pi's. 2 edge devices, and 1 cloud server.

Sensor Pi with Sonar Sensor that sends data to HUB to activate the actuator.

Stepper Motor Pi that activates upon receiving a query from the HUB.

Cloud Server Pi that sends/receives information from HUB Pi and desplays them in a web client that can be accessed by user.

# Getting Started
## Setting Up Bluetooth on the HUB, Sensor Pi, and Servo Motor Pi
### Installing Bluez
If you have a Raspberry Pi 3B or later, then you should have bluetooth installed. You can check to see what version you have by typing `bluetoothd --version`
The version that we are using is version 5.50 for this project. If you're having issues with getting bluetooth working or don't have bluetooth installed, follow this tutorial on getting started with BlueZ:

https://3pl46c46ctx02p7rzdsvsg21-wpengine.netdna-ssl.com/wp-content/uploads/2019/03/1908_Tutorial-How-to-set-up-BlueZ__UpdateLFC_FINAL.pdf

`sudo apt-get install bluetooth bluez-utils blueman` will also be a good start to what we're going to be using bluetooth for.

### Programming with bluetooth for each Pi
A very helpful and insightful resource for programming with bluetooth was this website: https://people.csail.mit.edu/albert/bluez-intro/
We implement this code for connecting the Hub, Sensor, and Motor Pi's to each other to have basic communication with each other.
We chose to write the socket connection in C. Originally we were writing it in python, but we had plenty of stuff wrong with our own implementation and PyBluez' documentation wasn't particularly helpful, so we scrapped writing it in python and opted for C instead.

#### Servo Motor Pi

## Setting up Cloud4RPi on cloud and hub devices

https://docs.cloud4rpi.io/start/rpi/

## Setting up Apache on cloud raspberry pi
First things first, install apache `sudo apt install apache2 -y`. After installing, you can check to see that it installed correctly by typing `http://localhost` in a web browser, it should bring up the default Apache2 Debian page. Once that it done you can go to the directory `cd /var/www/html` and typing in `ls -al` to see the programs in the folder as well as the read and write permissions. We had nginx installed as well when we got apache2, so we had to disable that by removing that from the folder and typing `service nginx stop` to stop the process from running. The reason we wanted nginx to stop is because both Apache2 and nginx were listening to port 80 and nginx would stop Apache2 from running. I just did `sudo apt-get remove nginx` and now it's gone forever.
After removing nginx, we installed php so we can have php in the code `sudo apt install php libapache2-mod-php -y`. After installing php, we changed the index.html file `sudo nano index.html` and put in some php code to test and it worked.
Once we installed php, we installed mysql using mariadb which is associated with mysql. To install you type `sudo apt install mariadb-server`.


# Resources
Bluez: https://3pl46c46ctx02p7rzdsvsg21-wpengine.netdna-ssl.com/wp-content/uploads/2019/03/1908_Tutorial-How-to-set-up-BlueZ__UpdateLFC_FINAL.pdf

Programming with bluetooth: https://people.csail.mit.edu/albert/bluez-intro/

Cloud4RPi: https://docs.cloud4rpi.io/start/rpi/

Apache/PHP: https://www.raspberrypi.org/documentation/remote-access/web-server/apache.md

Mysql: https://pimylifeup.com/raspberry-pi-mysql/
