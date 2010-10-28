---
layout: post
title: AiGLX + Beryl
time: "17:43"
extended: ":EXTENDED:"
---

[Optical](http://linuxfire.com.cn/~optical/) has told me many times about the beryl.  But i just was reluctant to try new edge-sharping things and not much in the mood for maybe-complex-and-frustrating configuration/settings.  Well, you can calle me a 'old-fashioned' 'lazy-bone'.

But you are running `edgy` now!   Ok, sounds fair to try edge-sharping things on a distro called 'edgy'.   :^)

The process is, in fact, very simple, indeed:
just follow [this doc](http://wiki.beryl-project.org/index.php/Install/Ubuntu/Edgy/AiGLX).

No frustrating configs AT ALL.  For me using edgy, all i need to do is installing the `beryl` and `the emerald-theme` pkg.   Thats it.  No more effort.

And the first run is quite quite impressive.  I kindof expected some crash or non-working. But it turns out to be working pretty fine.  Well, not much to describe here.  This is kindof a unless-you-try-and-see-yourself thing.  Recommend you give it a try. Oh yes, that cube and those special effects.. Kool enough.


PS. 

Been using edgy for days.  Not bad indeed.  I have got used to the [apt-get](http://www.debian.org/doc/manuals/apt-howto/) stuff, installed some apps i need (namely my 'mail tool-chain': mutt, procmail, fetchmail, mstmp) and now i'm starting to feel comfortable in the environment.  (Yes, unlike ports-based bsd or crux, it does not have compile/build tools/headers/docs installed by default.  Well, thats a quite fair and sane choice for a pkg-based desktop system.  Easy to add any way, no need to say).

And that [`cpu soft lockup bug`](https://launchpad.net/distros/ubuntu/+source/linux-source-2.6.17/+bug/63418).  It's getting clear that it's the [fault of the ipw3945 driver](http://bughost.org/bugzilla/show_bug.cgi?id=1096).  Loading it at the boottime would trigger the bug.  [Patch](http://bughost.org/bugzilla/attachment.cgi?id=956) is available.  But i'm looking forward to the official ubuntu updates.

Another glitch is the sound problem concerning suspend/hibernate.  No sound after a resume.  Intel hda, maybe quite new for alsa.  Lets wait and see.

