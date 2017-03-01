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

### Some Python Notes

When you receive input from `raw_input` it will be a string, you would have to specify that you want it to be an integer or something yourself. So you could say `int(raw_input("Enter the first rod spec (in mm):"))` would return an int of whatever the user puts in.

##### EXCEPT! 

.. this is where you're starting to get into a new topic as well. That line of code is something that's very probable to have an exception. An exception is *thrown* when something happens that shouldn't, and the program needs to react to it.

```python
>>> int(raw_input('Hi there! '))
Hi there! Hi back!
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ValueError: invalid literal for int() with base 10: 'Hi back!'
```

That `ValueError` is an exception, and it gives an explanation that an "invalid literal for int()" was given

*Exception handling* is used to react to these types of problems as an after-the-fact kind of situation. The `ValueError` kind of means "The user gave you the wrong input". With exception handling, it's "The user gave you the wrong kind of input, what would you like to do about that?" To which you can be like, "Tell that motherfucker to put in valid numbers and let's start over!"

### A short example of exception handling:

```python
>>> try:
...   int(raw_input("Enter a measurement: "))
... except ValueError as v:
...   print("Motherfucker that's not a number!\n%s" % v)
... 
Enter a measurement: loljk
Motherfucker that's not a number!
invalid literal for int() with base 10: 'loljk' 
```
