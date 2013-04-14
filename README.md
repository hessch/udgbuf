UDGFB - Framebuffer using HD44780 User Defined Characters for Psion II 
======================================================================

Hessel Schut <hessel@isquared.nl>

(c) 2009,2013 isquared.nl, Licensed under Creative Commons CC BY-SA 3.0

UDGFB is a 20x16 framebuffer for Psion Organiser II devices based on the
eight user-defined characters or the Hitachi HD44780 LCD controller in these
devices.

The framebuffer uses the user-defined characters printed in the following
configuration:

	udg0 udg1 udg2 udg3
	udg4 udg5 udg6 udg7

See [this](http://isquared.nl/blog/2009/06/16/UDGBUF-Part-1.5-%3A-Adventures-with-the-HD44780/) and 
[this](http://isquared.nl/blog/2009/06/13/UDGBUF%3A-a-poor-man's-framebuffer-on-Psion-Organiser-II-Part-1/) blog posts for more details.

The following functions are defined:
- clearfb:
  --------
  clears the framebuffer

- printfb:(xpos, ypos) 
  --------------------
  print framebuffer UDGs at location (xpos, ypos)

- pset:(x, y, s)
  --------------
  set pixel at (x, y) to state s, where "s" is 0 or 1

- pixel%:(x, y)
  -------------
  get value of pixel at (x, y)

- blitup:
  -------
  scroll all pixels one row up, duplicates row 15

The following functions are for internal use:
- pokeudg:(char, row, value)
  --------------------------
  write value to udg row of udg character

- peekudg%:(char, row)
  --------------------
  read byte defining row of udg character

