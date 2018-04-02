Eggduino
====

Arduino Firmware for Eggbot / Spherebot with Inkscape-Integration

Version 1.6a
tested with Inkscape Portable 0.91, Eggbot Extension and patched eggbot.py

Regards: Eggduino-Firmware by Joachim Cerny, 2015

Thanks for the nice libs ACCELSTEPPER and SERIALCOMMAND, which made this project much easier. Thanks to the Eggbot-Team for such a funny and enjoyable concept! Thanks to my wife and my daughter for their patience. :-)

Features:

- Implemented Eggbot-Protocol-Version 2.1.0
- Turn-on homing: switch-on position of pen will be taken as reference point.
- No collision-detection!!
- Supported Servos: At least one type ;-) I use Arduino Servo-Lib with TG9e- standard servo.
- Full Arduino-Compatible. I used an Arduino Uno
- Button-support (3 buttons)

Tested and fully functional with Inkscape.

Installation:

- Upload Eggduino.ino with Arduino-IDE or similar tool to your Arudino (i.e. Uno)
- Install Inkscape Tools wit Eggbot extension. Detailed instructions: (You yust need to complete Steps 1 and 2)
http://wiki.evilmadscientist.com/Installing_software
tested with  https://github.com/evil-mad/EggBot/releases/tag/2.7.1 

- to get it run with the uno you have to edit the file: ebb_serial.py in the extension folder:

	in the function findPort you change the line:
	if port[1].startswith("EiBotBoard"):  
		to 
	if port[1].startswith("USB2.0-Serial"):
	
	just change the String keep all blanks.
	
	in the function testPort you change the line
	
	serialPort = serial.Serial( comPort, timeout=1.0 ) # 1 second timeout!
		to
	serialPort = serial.Serial( comPort, baudrate=9600 ,timeout=1.0 ) # 1 second timeout! 
	
	
	


