# DIY Home Assistant Cat Feeder - Using ESPHome and Home Assistant. WORK IN PROGRESS!
This catfeeder features quite a lot of tech! Besides its main funtion of a feeder itself, it also has:<br>
An ultrasonic sensor to tell us when the feeder is low^.<br>
And ESPHome to tie it into your Home Automation system!<br>
And it is really cheap!

# Functions:
* Feeding the cat by manual operation or automated by HA.
* Measure remaining food by ultrasonic
* Notify via Alexa TTS and Telegram about remaining food
* Whatever you can imagine with Home Assistant!


Thanks for checking this out! Here is what my prototype cat feeder looks like:
HA:
<a href="https://imgur.com/LjEK2e0"><img src="https://imgur.com/LjEK2e0.jpg" title="source: imgur.com" /></a>
Hardware:
<a href="https://imgur.com/kGHy0tY"><img src="https://imgur.com/kGHy0tY.jpg" title="source: imgur.com" /></a>

# Here's what you need for hardware:
-  1x NodeMCU v3 ESP8266 (I use an Lolin NodeMCU, but any NodeMCU or WeMos D1/ D1 Mini will work) https://ebay.us/EqwFiP ~5€
-  1x Servo Motor Continuous SM-S4303R: https://amzn.to/2YpssPv ~10€
-  1x Ultrasonic Module HC-SR04 Distance Transducer Sensor For Arduino Robot  https://ebay.us/ei9Pcy ~2€
-  1x Whatever Smartphone Charger https://amzn.to/2OTBqS0 ~15€
-  1x takestop Dry-Food Dispenser https://amzn.to/2YlzHs1 ~15€
-  Various header wires (male-male, male-female, female-female)
-  A USB-A to Micro USB cable.
-  Dremel or drill.

Around 35€ if you a have a spare charger at home. Even cheaper if you get bulk sensors and Lolins or WeMos from Bangood or Aliexpress. The most expensive item is the Dispenser and usually they arren't very well made... But if we got the mechanics and automations, a cilinder and a D shape rotary axis is really easy to make in 3d ;)

# Currently working on::
* Script to rotate at input_number.servo_control (speed) during input_number.servo_time (seconds) the stop. Due to few resources about continuous rotors in EspHome
* Automation based in time (Easy part ;))
* Last time executed sensor

# Todo List:
* Some scale or sensor to detect the bowl placed below, to stop the automation if not or if it full.
* Some 3d printing:
  * Lolin case: https://www.thingiverse.com/thing:2850128
  * Servo mount: https://www.thingiverse.com/thing:3269637
* Automate my excel list my food providers to automatically show the cheapest one and trigger it by a commmand on Telegram/HA.

# Building it!
* Compile the code inside EspHome and download the binary to install it with EspHome Flasher.
* Fit the ultrasonic sensor below the lid with screws, some hot glue, whatever fits for you.
* With a drill or dremel, drill a passthrough to connect the ultrasonic sensor to the Lolin. I use four pins, to make it detachable.
<a href="https://imgur.com/5NPo7WZ"><img src="https://imgur.com/5NPo7WZ.jpg" title="source: imgur.com" /></a>
* Screw the servo motor to the rotary handle.
<a href="https://imgur.com/yUB9Slp"><img src="https://imgur.com/yUB9Slp.jpg" title="source: imgur.com" /></a>
* Connect the pins as set below.
* Connect your MicroUSB 
* Create the package for Home Assistant and restart the server.
<a href="https://imgur.com/FNGvack"><img src="https://i.imgur.com/FNGvack.png" title="source: imgur.com" /></a>
