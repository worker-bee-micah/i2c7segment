This is a library for using the Adafruit i2c 4 digit 7 segment LED displays
with i2c on a Raspberry Pi. It was built and tested on Raspbian Wheezy.

This is not an Adafruit product.

To get i2c to work, you need Raspbian Wheezy or later and to do:
```
 sudo apt-get install python-smbus
 sudo apt-get install i2c-tools (usefull but not essential)
 sudo modprobe i2c-dev
 sudo modprobe i2c-bcm2708
```

Example Usage:

```
disp = Adafruit7Segment()
raw_input("print_int(65535, 16)")
disp.print_int(65535, 16)
disp.write_display()
raw_input("print_int(1234)")
disp.print_int(1234)
disp.write_display()
raw_input("print_str(----)")
disp.print_str('----')
disp.write_display()
raw_input("print_str(-12.3)")
disp.print_str('-12.3')
disp.write_display()

```

Methods:

```
set_brightness(brightness)
"""Set brightness 0 to 15"""

set_blink_rate(blink):
        """Blink Rate 0, 1 or 2"""

write_digit_raw(digit, bitmask):
        """ Write the LED segments for a digit directly dp g f e d c b a """

write_digit_num(digit, number, dot=False):
        """ Write a number into a digit position optionally with a dot"""

raw_colon(show_colon):
        """ Turn the colon in the middle on or off"""

write_display():
        """ Refresh the display - nothing will appear until you call this"""

print_int(n, base=10):
        """ Pint the integer, optionally with number base (2..16)"""

print_str(s):
        """
        Do the best you can with a 4 digit string (more with dots)
        this is how you deal with floats and signs etc
        format it first then print it
        unknow characters print as a space



```

Simon Monk http://www.simonmonk.org Please give credit where credit is due.