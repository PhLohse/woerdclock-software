Serial Communication Modul for Wördclock
===================

is a part of wördclock, a Arduino powered and WS2812B featured Wordclock.

This is the Serial Communication Modul for Wördclock v0.5 by Marcel Müller.
It based on parser for serial communication on Arduino by (c) 140801 Thomas Peetz

wc_serial_mode is the main programm.
wc_serial_mode can use three functions:

Serial1_interprete
to interprete command from bluetooth (pin 0,1)

Serial_interprete();
to interprete commands from serial port (usb)

BTSerial_interprete()
to interprete commands from bluetooth (pin 9,8)

The default BAUDRATE is 9600 for all functions.

If comment a function out, you can use only the other ways.

Actually, wifi is not implementet, comming soon.



The communication works passive.
Send a command and you get an answer.
For example, to check the actual color of the leds type glc for get_led_color.
You get the values for R,G,B.
This data was read from SRAM.

You can change the color with slc (=set_led_color).
For example, to get a nice red:
slc=255,0,0

This data is stored in SRAM only.
For permanent storage use slcp.
The data will be copied from SRAM to EEPROM.
The EEPROM memory has a specified life of 100,000 write/erase cycles, 
so you may need to be careful about how often you write to it.
You can check the color in EEPROM with glcp.

You can do all the same with the led brightness.


Implemented commands are
  show = show status
  help = help text
  
  slb = set_led_brightness (store in SRAM)
  glb = get_led_brightness (get from SRAM)
  
  slbp = set_led_brightness_permanent (store in EEPROM)
  glbp = get_led_brightness_permanent (get from EEPROM)
  
  slc = set_led_color (store in SRAM)
  glc = get_led_color (get from SRAM)
  
  slcp = set_led_color_permanent (store in EEPROM)
  glcp = get_led_color_permanent (get from EEPROM)
