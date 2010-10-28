---
layout: post
title: Avant and Screenlets
time: "14:05"
extended: ":EXTENDED:"
---

Surfing on the web, i just came across a kool dockbar (like OS X's) for gnome: [avant-window-navigator](http://code.google.com/p/avant-window-navigator/).  And from [this thread showing the screenshots](http://www.planetblur.org/hosted/awnforum/index.php?shard=forum&action=g_reply&ID=18&page=1&isLive=true)  of avant, just found another kool stuff called [Screenlets](http://compiz.org/Desktop_Screenlets) (like OS X's dashboard).

Now how to install and use these two:

1) For avant, luckily there are ubuntu [pkg/repos](http://awn.wetpaint.com/page/Ubuntu) for it. After installation (you know it), you can start it from menu Application-> Accessories ->  Avant Window Navigator, or simply run 

     $ avant-window-navigator
 
to launch it.   Easy, kool and no pain.  It works well with Beryl's preview feature. Neat!

And what makes it more like OX's dockbar, it can have launchers too!  Just drag apps from menu or the shortcuts to the bar.  Nice.   Here's a [screenshot](http://linuxfire.com.cn/~alecs/pics/avant-with-launcher.png).  On the right side of the separator are the opened windows of non-launcher apps. Launchers are always on the left, opened or not.  The difference is that not-opened launcher has  an arrow under the icon.  All these arrangements are quite like those of OS X's. If you want to start another instance of already opened launcher, use middle-click instead of regular left-click. (Ah, this  isnt like OS X, for mac mice have only one button..:^) The only lacked feature is mac's pretty 'smooth scale' of icons on the bar.  Hope to see that in the next release.

2) For screenlets, there's an [edgy repo](http://syzygy42.tuxfamily.org/dists/edgy/screenlets/) for it.  But no such pkg for feisty (well, for those who dont know, i updated to feisty quite long ago..  uhoh, how many days without writing the blog..). So i downloaded [the source](http://www.ryxperience.com/storage/screenlets-0.0.7.tar.bz2) (0.0.7) and manually installed it (regular python stuff, very easy).  

Run

    $ screenletsd start

to start the daemon. But when i was to start any widget by running

    $ screenletsd add blah

i met the following error:

    No handlers could be found for logger "dbus.proxies"
    Error: Screenlets-Backend (screenletsd) not found.

After some searching, found this [page](http://forum.go-compiz.org/viewtopic.php?t=358&postdays=0&postorder=asc&start=360&sid=6242474ce53e65d8a5428423572ce27f), where RYX spotted the tiny bug. If you have similar error (my environment is feisty with python2.5), you may try [this patch](http://linuxfire.com.cn/~alecs/patch/screenlets-0.0.7-tinyfix).

Use

    $ screenlets add Control

to start the main control utility, or

    $ screenlets add Clock

to start specific widget.

And there are more goodies in the [screenlets-extras](http://download.tuxfamily.org/syzygy42/pool/edgy/screenlets/screenlets-extras_0.0.7-5.tar.gz) (including calender, weather, etc.).  If you are using edgy, you can install pkg from the [repo mentioned above](http://syzygy42.tuxfamily.org/dists/edgy/screenlets/).

Screenlets really feels very smooth and modern! I used to use [gDesklets](http://www.gdesklets.de/) to get similar function.  But (not in offense), gDesklets really is not Good Enough (TM).  It feels very flat and rigid.  Another good thing about screenlets is that, not like gDesklets, you can freely move them just like other apps.  With beryl's special window moving effect, it's really nice.

Here are two screenshots, one showing the [old gDesklets](http://linuxfire.com.cn/~alecs/pics/oldgdesklets.png) and the other showing [Screenlets and Avant with Beryl](http://linuxfire.com.cn/~alecs/pics/newscreenlets-avant-beryl.png).   Oh, dont get confused by the desktop background.  Im not running SuSE Enterprise. Im running ubuntu feisty. I just like the [wallpaper](http://www.novell.com/company/logo/). It (the orange) suits well the ubuntu's human theme.  Screenshot is merely a static view (better make some video demos).  You'd better install and try these stuff yourself to 'get a feel'.

Speaking of beryl, it really gets stable these days.  The new tabring (windows key + tab) and window preview features are handy and pretty.  Love them.  And btw, I'm now using the [vista-q](http://gnome-look.org/content/show.php?content=42875) emerald theme.

Bottom line: Beryl + Avant + Screenlets is really the way to go.

PS, seems [avant's author](http://njpatel.blogspot.com/) has other interesting projects to play with.  Maybe i'll give his [Affinity](http://code.google.com/p/affinity-search/) a shot.

