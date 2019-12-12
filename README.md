# DIY Home Assistant Cat Feeder - Using ESPHome and Home Assistant. WORK IN PROGRESS!
This catfeeder features quite a lot of tech! Besides its main funtion of a feeder itself, it also has:<br>
An ultrasonic sensor to tell us when the feeder is low.<br>
And ESPHome to tie it into your Home Automation system!<br>
And it is really cheap!

# Functions:
* Feeding the cat by manual operation or automated by HA.
* Measure remaining food by ultrasonic
* Notify via Alexa TTS and Telegram about remaining food
* Whatever you can imagine with Home Assistant!
* Can run from a USB Powerbank, so it can run on the go or as a security feature as UPS


Thanks for checking this out! Here is what my prototype cat feeder looks like: <br>
HA: <br>
<a href="https://imgur.com/Kehp6hD"><img src="https://imgur.com/Kehp6hD.jpg" title="source: imgur.com" /></a> <br>
The cards named "test" is under a tab named development, so I can control and calibrate all the values from here, while I only show the "pretty" card in the main screen. <br>
Hardware:<br>
<a href="https://imgur.com/kGHy0tY"><img src="https://imgur.com/kGHy0tY.jpg" title="source: imgur.com" /></a><br>

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

# Here's what you need for software:
-  <a href=https://www.home-assistant.io/>Home Assistant</a>
-  <a href=https://www.home-assistant.io/>EspHome</a>
-  <a href=https://github.com/custom-components/alexa_media_player> Alexa Media Player </a>
-  <a href=https://www.home-assistant.io/integrations/telegram/> Telegram notify in Home Assistant </a>

# Currently working on:
* Clean ultrasonic values (no negative values, no over 100% values)
* Automate my excel list with my food providers to automatically show the cheapest one and trigger it by a commmand on Telegram/HA. Also scrapping prizes?

# Todo List:
* Some scale or sensor to detect the bowl placed below, to stop the automation if not or if it is full.
* Some 3d printing:
  * Lolin case: https://www.thingiverse.com/thing:2850128
  * Servo mount: https://www.thingiverse.com/thing:3269637


# Thanks of the amazing work by:
* <a href=https://adonno.com/salt-level-sensor/>Adonno salt meter</a> 
* <a href=https://github.com/lance36/catFeeder/blob/master/catFeeder.ino>Lance36 catFeeder, my original inspiration</a> 
* <a href=https://github.com/335iguy/diy-multisensor-cat-feeder>335iguy, with a very similar approach</a> 
* The amazing Community of Home Assistant!!:
  * Forum: https://community.home-assistant.io/
  * Discord: https://discordapp.com/invite/c5DvZ4e
  * Reddit: https://www.reddit.com/r/homeassistant/
* Automate my excel list with my food providers to automatically show the cheapest one and trigger it by a commmand on Telegram/HA.

# Building it!
* Compile the code inside EspHome and download the binary to install it with EspHome Flasher.
* Fit the ultrasonic sensor below the lid with screws, some hot glue, whatever fits for you.
* With a drill or dremel, drill a passthrough to connect the ultrasonic sensor to the Lolin. I use four pins, to make it detachable.<br>
<a href="https://imgur.com/5NPo7WZ"><img src="https://imgur.com/5NPo7WZ.jpg" title="source: imgur.com" /></a><br>
* Screw the servo motor to the rotary handle.<br>
<a href="https://imgur.com/yUB9Slp"><img src="https://imgur.com/yUB9Slp.jpg" title="source: imgur.com" /></a><br>
* Connect the pins as set below.
* Connect your MicroUSB 
* Create the package for Home Assistant and restart the server.<br>
<a href="https://imgur.com/FNGvack"><img src="https://i.imgur.com/FNGvack.png" title="source: imgur.com" /></a> <br>
* Test your values with the test-card and hardcode the correct values as initial number in each input_number.<br>
* Define your automation<br>
