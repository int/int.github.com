---
layout: post
title: Kernel with no initird or module
time: "16:14"
extended: ":EXTENDED:"
---

> In those good old days,  
> when men were men and women were women,   
> when the sky was clear and the sex was dirty.

And [in those good old days](http://linuxfire.com.cn/~alecs/mtblog/2005/06/distro_of_choice.html), there was no initrd, nor kernel module.  We ran a plain kernel that  contained just those things we wanted, no more no less.

Ubuntu provides a generic kernel with a initrd and tons of modules for everyone.  That's perfectly good and sane for a distro vendor.  But not when you are in the mood to customize your kernel.  And with 2.6.21's [tickless](http://lwn.net/Articles/223185/) option and ck's new [SD scheduler](http://ck.kolivas.org/patches/staircase-deadline/) and improved [swap prefetch](http://ck.kolivas.org/patches/swap-prefetch/), i'm pretty much (once again) 'in the mood'.  And 2.6.22-rc1 has [a lot of tempting stuff](http://lwn.net/Articles/234123/) too.

OK, there's a [how-to-compile-your-kernel-the-ubuntu(debian)-way](http://www.howtoforge.com/kernel_compilation_ubuntu).  It's again perfectly good for a kernel package builder since it kinda hinds all the dirty stuff underhood  and builds the kernel as a .deb so that you can easily install/remove it using dpkg. But not for me, especially when it first do a 'make clean' that removes all the (good) old .o files everytime it compiles a kernel, even if just a single source file or config option is changed/added.  Oh no, those .o files are really supposed to be reused if possible (thats quite what 'make' is meant to do in the first place: reduce unnecessary recompilation).

I'd much like a 'make oldconfig && make' way to compile my kernels, fast, simple and 'hardcore'.  Based on one config file from [Optical](http://linuxfire.com.cn/~optical/) for his laptop, i tuned it to fit my box (mine is mostly an all-Intel, sound/video/network card, sata drive chips, etc).  And as a side-effect, i took it as a chance to remove any unnecessary options i dont actually need.  Went thru the menu config, deleted any 'fancy' stuff no use for me and made whatever i need directly compiled into kernel (=y not =m).

cp the bzImage and edit (ok, i mean vi) your bootloader config file.  Mine is grub (which is the ubuntu's default). Just two things to note since we've got no initrd now and grub directly boots the plain kernel:

1. usplash does not work since it (by design) needs the files in the initrd; disable it.
2. uuid for grub wouldnt do, since that again needs initrd (grub doesnt get the id itself but instead via udev in the initrd); use the real path for the root (ie. /dev/sda2).


Why bother?  
Because It's simple, clean and fast.


> One world, one dream,  
> One ring^Wkernel to rule them all.

