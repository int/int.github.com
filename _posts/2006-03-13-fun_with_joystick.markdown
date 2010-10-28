---
layout: post
title: Fun with Joystick
time: "10:53"
extended: ":EXTENDED:"
---

I recently bought a (cheap) joystick and really had fun with it on Linux. It's
a general USB HID Gamepad, no extra driver needed as long as your kernel has
USB HID builtin (normally it already has).  Besides this, just set
`CONFIG_INPUT_JOYDEV=y` to make kernel create a joystick device by which
userland apps communicate with kernel and thus make your joystick work as you
intend to.

Take a look at Documentation/input/joystick.txt. There you can
see a program called
[jstest](http://atrey.karlin.mff.cuni.cz/~vojtech/joystick/).
Download the tarball, compile the jstest.c and then run it to config your
joystick settings. (ie. Mine for example uses axe 4, 5 for h & v directions.)

My old xmame does not have joystick builtin so i grab the new source and
re-compile it.  Remember to enable `JOY_STANDARD = 1`.  Once it gets built, run
the xmame with options like this (or put them to your ~/.xmame/xmamerc):

	$ xmame -jt 1 -jdev /dev/input/js0 blah

(You might at first need to config the xmame joystick settings, no big deal).

Just playing metal slug under xmame with your joystick doesnt make you feel
'kool enough'?  How about surfing the web using your joystick as a mouse?

There's a nifty program called
[js2mouse](http://free.the.cube.free.fr/downloads/) to let you make a
joystick 'yet another mouse'.  It simulates a mouse via a fifo from reading
your joystick movements.  Read its docs while you compiling it. =)

1\. Write a /etc/j2m_map suiting your joystick config:

	button_1 = click_left
	button_2 = click_right
	button_3 = click_middle
	button_5 = wheel_up
	button_6 = wheel_down
	button_7 = click_extra1
	button_8 = click_extra2
	axe_4 = move_horizontal
	axe_5 = move_vertical

2\. Add some new entries to your X config:

	Section "InputDevice"
		Identifier  "Mouse2"
   		Driver      "mouse"
		Option "Protocol"    "IMPS/2"
		Option "Device"      "/dev/j2m_fifo"
		Option "ZAxisMapping" "4 5"
	EndSection

	InputDevice "Mouse2" "SendCoreEvents"

This will make your joystick the secondary mouse. If you want it become the
only main mouse. Disable your 'Mouse1' and make 'Mouse2' a 'CorePointer':

	InputDevice "Mouse2" "CorePointer"

And btw, that 'j2m_fifo' path is not hard coded, you can specify it to
any place where you have proper permissions
(and tell js2mouse via the option -f).

3\. Before you start X, run a command like:

	$ js2mouse -r -p imps2 &

Sweet.  Now you can use your joystick to do whatever you'd do with a common
mouse: point your 'joystick mouse' somewhere and double-cli^H^H^Hattack
to start apps, view docs using joystick 'wheel_up & downs', etc.

See js2mouse -h, its docs and source code for more details.


