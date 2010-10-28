---
layout: post
title: "Ubunu 6.10 -- first impression."
time: "01:34"
extended: ":EXTENDED:"
---

OK, yes, finally i tried out ubuntu..

The thing is i've got a new box and i just try to use it as a 'typical desktop' on a daily-base.  And Ubuntu may be the best distro 'known' for this kind of  stuff.  [Ubuntu 6.10](http://www.ubuntu.com/news/610released) just got released for days. Downloaded the iso, burned the cd, booted and ran.

The installation is fairly simple and starightforward.  Good enough for a newbie who's first time installing linux maybe.  Yes, i'm a text-junkie, but FYI, i can deal well with GUIs. j/k.

The first boot is quite impressive. Quite 'desktop-ish'. Indeed feels very modern. I like it.  Havent been for ages using Gnome.  It gets more polished and smooth now.  And ubuntu tinkered it quite seamlessly. And it seems to support all my hardwares 'out-of-box'. Tested the 'hibernate' and 'suspend' and both worked fine.

What strikes me more is the configuration part.  I'm very used to simple text-editing configuration (the way BSD or crux does).  Kinda lost in front of a new distro with a new system tree layout.  Some config files are still in same or similar locations while a lot remain to dig more.  For desktop things, i tweaked some font configurations (copied my old lovely local.conf from the crux box, added some Chinese fonts and changed the fonts.conf accordingly).  FYI, i like to use English locale while still being able to read and type Chinese properly and hopefully beautifully.  The Chinese ubuntu [forum](http://forum.ubuntu.org.cn/) is a nice place to go if you've got any problem . Well, for a true desktop user, i should've used more click-and-run instead of open-and-edit.. So..

As the first step of being (or pretending to be) like a typical desktop man, i installed some apps (scim-pinyin, xchat, mplayer) from the menu 'Add/Remove'.  Not bad, you know i used to install things via ports (grin).  And then i just surfed the web around and chatted on the irc while logging to gtalk via gaim.  And yes, watched some movie clip.  All goes well.  I'm not saying it's better than my crux box but it's really 'good enough' and works pretty fine for me.

And for the bad part. The biggest problem i met is the box hanged after the first reboot:

    soft lockup detected on cpu#0

Quite annoying.  Searched the web and found that many ppl got this problem. And the  workaround is to disable the splash^W s/ext3/reiser/^W fat/ntfs-mounting^W ipw3945 auto-loading. 

And there's a little glitch about the firefox.  Dunno how ubuntu tweaked it, the new pages are opened in new windows but the settings are already default to 'new tab'.  Easy to fix though:  just select 'new window' and then 'new tab'.  Weird.

Well, overall ubuntu 6.10 is a fairly nice distro to play with.  Its hardware support is pretty good and its modern desktop is smooth and neat.  I here recommend you give it a whirl if you wanna try something new as a old-fashioned linux user or if you are new to linux and want a painless conversion from The OS Which Must Not Be Named.

Stay tuned and hopefully i'll find out more.

