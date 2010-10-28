---
layout: post
title: Replace devfs with udev on crux
time: "02:01"
extended: ":EXTENDED:"
---

As of 2.6.13-rc1, devfs is not supported, at least gets <a href=http://kernel.org/git/?p=linux/kernel/git/torvalds/linux-2.6.git;a=commit;h=2c6e5a839f92591a4bc6cac4a575d42151645af3>removed from Kconfig</a>. Crux by default is using devfs.  But the migration is not hard.

1) enable CONFIG_HOTPLUG, disable CONFIG_DEVFS_FS

2) # prt-get depinst udev

3.1) edit /etc/rc, /etc/rc.single

        - # Start device management daemon
        - /sbin/devfsd /dev

        + # Start udev
        + /bin/mount -t sysfs none /sys
        + /bin/mount -t proc none /proc
        + /sbin/start_udev

3.2) in /etc/fstab,  comment or remove the /sys & /proc entries, and then add or change the /dev/pts entry:

        none /dev/pts devpts defaults 0 0

4) create an 'audio' group and add revelant users, ie.

        # groupadd audio
        # usermod -G audio alecs

btw,  the default values of /etc/udev/rules.d/50-udev.rules are really very sane.  I just dont have to edit anything (ie. nvidia, /dev/snd/*) .

Reference: /usr/ports/contrib/udev/README

