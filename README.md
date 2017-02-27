# rpi-stack

### Hardware Setup:
* Model: Raspberry Pi 3 Model B
* Operating System: [Raspbian](https://www.raspberrypi.org/downloads/raspbian/)
* SD Card: 8GB+
* Installation:
  * Raspbian: https://www.raspberrypi.org/documentation/installation/installing-images/README.md
  * NOOBS for Easier Install: https://www.raspberrypi.org/downloads/noobs/

*Keyboard/Display for Setting Up*

### Python Setup:
*Python should be included in Raspbian.* There are two versions however, and Python 3 is the newer and standard version. 

* Installing Python packages: https://www.raspberrypi.org/documentation/linux/software/python.md
* RPi.GPIO Python package: https://pypi.python.org/pypi/RPi.GPIO
* Examples: https://sourceforge.net/p/raspberry-gpio-python/wiki/Examples/

### Example Projects on GitHub Using Python GPIO:
* [List of a couple dozen projects with various devices](https://github.com/Dayanand-Patil/Raspberry-Pi)
* [Robot Car](https://github.com/jovanailic993/RaspberryPi-robot-car)
* [Motorcycle Sensor](https://github.com/craigfortune/MotorcycleLeanSensor)
* [GPIOExamples](https://github.com/williamhbell/GpioExamples)
* [RPi Interfacing](https://github.com/BirchJD/Raspberry-Pi-Python-Interfacing)

### Possible Ideas:
* [Use a more user-friendly device interface](https://github.com/RPi-Distro/python-gpiozero). This one makes using connected devices much simpler, with modules for LEDs, [range sensors](https://www.amazon.com/HC-SR04-Ultrasonic-Distance-MEGA2560-ElecRight/dp/B01MA4O5G5/ref=sr_1_2?ie=UTF8&qid=1487357864&sr=8-2&keywords=HC-SR04), [motors](https://gpiozero.readthedocs.io/en/v1.3.1/api_output.html#motor), and [more](https://gpiozero.readthedocs.io/en/v1.3.1/index.html). This one looks very promising to start off with. If something is mentioned in the module (such as the range sensor, which has a specific model given), try to get that. 

### Copying your script to the Raspberry Pi:

With the IP address of the Raspberry Pi as `$pi_addr`, and script name as `$py_script`, ie. `egr_script.py`

1. Open a terminal
2. Navigate to the directory your Python script is
3. Run the following, and enter the password when prompted:

```sh
scp $py_script pi@$pi_addr:/home/pi
```

Your script should now be on the Raspberry Pi under the `/home/pi` directory!

### Getting the IP address of your Raspberry Pi:

The IP address can be found under the `wlan0` hardware using the command `ip a`. 

If there is no IP address here, you still need to connect to the network, so checkout [Connecting to a network](#).

