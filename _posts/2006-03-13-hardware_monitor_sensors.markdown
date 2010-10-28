---
layout: post
title: Hardware Monitor Sensors
time: "14:04"
extended: ":EXTENDED:"
---

I use [conky](http://conky.sourceforge.net)
to monitor various system/hardware infos like cpu/mem/swap
usage, networking loads, etc.  But seems my kernel (adapted from a CRUX
default config) has not yet compiled in hardware sensor support
and thus conky cannot
show cpu temperature correctly.  Well, it's easy to add such function.

First download the [lm-sensors](http://secure.netroedge.com/~lm78/)
and then compile and run the
`sensors-detect` command.  Follow what that command prompts you and normally
it would give you the proper sensor types.

For example, mine is a w83627hf isa sensor.  On the kernel side, you'd need
the following options:

	CONFIG_I2C=y
	CONFIG_I2C_ALGOBIT=y
	CONFIG_I2C_ISA=y
	CONFIG_HWMON=y
	CONFIG_HWMON_VID=y
	CONFIG_SENSORS_W83627HF=y

You can easily select them from kernel's menuconfig (mainly I2C, Hardware
monitor and the specific sensor).

Rebuild the kernel and you can get the various sensor info.  Without any
extra config conky works fine accordingly.  Run the command `sensors` from
the lm-sensors pkg you can get more info (it actually just reads info from
a sensor device entry under your /sys, ie, mine is at
/sys/devices/platform/i2c-9191/9191-0290/)


