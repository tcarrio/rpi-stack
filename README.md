# rpi-stack

Hardware Setup:
* Model: Raspberry Pi 3 Model B
* Operating System: [Raspbian](https://www.raspberrypi.org/downloads/raspbian/)
* SD Card: 8GB+
* Installation:
  * Raspbian: https://www.raspberrypi.org/documentation/installation/installing-images/README.md
  * NOOBS for Easier Install: https://www.raspberrypi.org/downloads/noobs/

*Keyboard/Display for Setting Up*

Python Setup:
*Python should be included in Raspbian.* There are two versions however, and Python 3 is the newer and standard version. 

* Installing Python packages: https://www.raspberrypi.org/documentation/linux/software/python.md
* RPi.GPIO Python package: https://pypi.python.org/pypi/RPi.GPIO
* Examples: https://sourceforge.net/p/raspberry-gpio-python/wiki/Examples/

Example Projects on GitHub Using Python GPIO:
* [List of a couple dozen projects with various devices](https://github.com/Dayanand-Patil/Raspberry-Pi)
* [Robot Car](https://github.com/jovanailic993/RaspberryPi-robot-car)
* [Motorcycle Sensor](https://github.com/craigfortune/MotorcycleLeanSensor)
* [GPIOExamples](https://github.com/williamhbell/GpioExamples)
* [RPi Interfacing](https://github.com/BirchJD/Raspberry-Pi-Python-Interfacing)

Possible Ideas:
* [Use a more user-friendly device interface](https://github.com/RPi-Distro/python-gpiozero). This one makes using connected devices much simpler, with modules for LEDs, [range sensors](https://www.amazon.com/HC-SR04-Ultrasonic-Distance-MEGA2560-ElecRight/dp/B01MA4O5G5/ref=sr_1_2?ie=UTF8&qid=1487357864&sr=8-2&keywords=HC-SR04), [motors](https://gpiozero.readthedocs.io/en/v1.3.1/api_output.html#motor), and [more](https://gpiozero.readthedocs.io/en/v1.3.1/index.html). This one looks very promising to start off with. If something is mentioned in the module (such as the range sensor, which has a specific model given), try to get that. 
