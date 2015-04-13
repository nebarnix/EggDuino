Eggduino (Nebarnix's Laser/Servo Rate Fork)
====

Arduino Firmware for Eggbot / Spherebot with Inkscape-Integration

Version 1.4n
tested with Inkscape Portable 0.91, Eggbot Extension and patched eggbot.py

This fork by Nebarnix implements a servo rate control, as a percentage of full speed, so you can slow down the pen up and pen down (they were much too fast without it)

This changes pins around from the parent project, sorry about that. This also implements a laser out PWM signal to laser engraving eggs or ablating dye from eggs. Have fun and be safe, always wear eye protection and warn others BEFORE they come into visual range!

Regards: Eggduino-Firmware by Joachim Cerny, 2015

Thanks for the nice libs ACCELSTEPPER and SERIALCOMMAND, which made this project much easier. Thanks to the Eggbot-Team for such a funny and enjoyable concept! Thanks to my wife and my daughter for their patience. :-)

Features:

- Implemented Eggbot-Protocol-Version 2.1.0
- Turn-on homing: switch-on position of pen will be taken as reference point.
- No collision-detection!!
- Supported Servos: At least one type ;-) I use Arduino Servo-Lib with TG9e- standard servo.
- Full Arduino-Compatible. I used an Arduino Uno

Tested and fully functional with Inkscape.

Installation:

- Upload Eggduino.ino with Arduino-IDE or similar tool to your Arudino (i.e. Uno)
- Disable Autoreset on Arduinoboard (there are several ways to do this... Which one does not matter...)
- Install Inkscape Tools wit Eggbot extension. Detailed instructions: (You yust need to complete Steps 1 and 2)
http://wiki.evilmadscientist.com/Installing_software

- Because of an bug in the Eggbot-extension (Function findEiBotBoards()), the Eggduino cannot be detected by default.
	Hopefully, the guys will fix this later on. But we can fix it on our own.
    It is quiete easy:
	
        - Go to your Inkscape-Installationfolder and navigate to subfolder .\App\Inkscape\share\extensions
		- open File "eggbot.py" in texteditor and search for line:
			"Try any devices which seem to have EBB boards attached"
                - comment that block with "#" like this:
                		# Try any devices which seem to have EBB boards attached
				# for strComPort in eggbot_scan.findEiBotBoards():
				#	serialPort = self.testSerialPort( strComPort )
				#	if serialPort:
				#		self.svgSerialPort = strComPort
				#		return serialPort
		- In my version lines 1355-1360
 
Todos and Feature-Wishlist:

- implement hardware-button , EGGBOT-Guys call it "PRG-Button"
  
