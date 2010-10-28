---
layout: post
title: Install, Boot, Run
time: "15:49"
extended: ":EXTENDED:"
---

Installing linux is much more easier these days.  LiveCD is now becoming a de facto standard.  Some distro even provides a LiveUSB.  If not, here's a great tool that can help you make a liveusb from a livecd image, automatically: [unetbootin](http://unetbootin.sourceforge.net/).

Besides the usblive feature, it also supports install-from-net, install-from-windoze, install-from-disk, etc.  If you like to try installing different distros and dont have a CD drive (or dont like to burn CDs), unetbootin is your friend. 

Big distros nowadays are all trying hard to make the booting fast: kernel-mode-setting, init-ng, readahead, parallel loading, etc.  Here's a great tool that can monitor and visualize the booting process:  [bootchart](http://www.bootchart.org/).  I upgraded to [Intrepid](http://www.ubuntu.com/products/whatisubuntu/810features/) weeks ago.  And here's a [bootchart shot](http://linuxfire.com.cn/~alecs/pics/intrepid-20081113-1.png).

35 seconds: a cold start, from boot to xorg/gdm running with all common services and wireless network up.  I'm very pleased with this, considering its a ubuntu default kernel, default initrd with default settings.  If you customize your kernel building all needed drivers in with [no module or initrd](http://linuxfire.com.cn/~alecs/blog/2007/05/kernel-with-no-initird-or-module.html), and use a slimmed down DE/WM without many startup services, it may reduce about 10 seconds i guess.

And speaking of wireless network, i've been using [network-manager](http://projects.gnome.org/NetworkManager/) for a long time (since edgy?) It works fine (well, though not as half good as AirPort). But not for me in intrepid.   Authentication goes well but it fails requesting an ip address. I dunno why. Maybe the kernel, the iwl driver, the wireless router or the nm itself. Dont bother to figure it out or use the cmd line (iwconfig,  wpa_supplicant, etc.).  Bad me, I am a typical desktop linux user now. Here's a replacement:  [wicd](http://wicd.sf.net).  It works well. No bloat. Kool.

And finally, here's a tool called [smolt](http://smolt.fedoraproject.org/) which can gather your hardware information and submit it to its central database.  You can see [some stats](http://smolt.fedoraproject.org/static/stats/stats.html) and [devices information](http://smolt.fedoraproject.org/static/stats/devices.html).  Maybe not directly good for you but it helps the community in the long run.


