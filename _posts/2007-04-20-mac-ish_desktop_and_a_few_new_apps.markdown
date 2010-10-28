---
layout: post
title: "Mac-ish desktop and a few new apps"
time: "17:20"
extended: ":EXTENDED:"
---

Now that i've installed [avant and screenlets](http://linuxfire.com.cn/~alecs/mtblog/2007/04/avant_and_screenlets_1.html),
lets be more mac-ish.

[This article](http://www.taimila.com/osx-guide-2.php) is a step-by-step guide helping you to do the mac-on-ubuntu, neatly.  From the booting to the icons, all bits included. The best part i like is the [gtk theme](http://www.taimila.com/downloads/gtk-osx-theme.tar.gz) that the author himself created.  I have tried many aqua-alike gtk themes before (mind you, back in the gtk1 days..) but none was as good as this one.  The button and scrollbar is very smooth.  You may also need the [old document](http://www.taimila.com/ubuntuosx.php) by the author too.

Just some notes not mentioned in the documents:

1. screenlets

2. for firefox, i didnt use compact menu extension the author suggested; instead, i used the [hide menubar extension](https://addons.mozilla.org/en-US/firefox/addon/4762).

3. from avant's preferences, disable 'rounded corner', set the arrow color to black, check 'tasks have arrows' and change the Gradient color.

4. [mac mouse theme](http://www.gnome-look.org/content/show.php/MacOSX+PantherX+Mouse+Theme%5BFor+Baghira%5D?content=13524). `gcursor` is a handy program helping you easily install/change mouse themes.

5. the usplash.  You need `libusplash-dev` to make the author's boot splash.  And run a `$ sudo ln -sf /usr/lib/usplash/osx-splash.so /etc/alternatives/usplash-artwork.so` before doing the `dpkg-reconfigure ...`.  Oh, speaking of usplash, here's a [coffee-beens theme](http://onlyubuntu.blogspot.com/2007/03/new-sleek-usplash-proposal-for-ubuntu.html).      
Note that the arguments of ln were (as of this writing) misordered. 

Here is a screenshot [showing the main desktop](http://linuxfire.com.cn/~alecs/pics/mac.png).  I didnt do the menubar part, since that requires to patch gtk.


These days i'm really much into the desktop things.  Surfing and lurking, i found some kool apps:

1. [Telepathy](http://telepathy.freedesktop.org/).  An IM framework. I dumped the buggy gaim and start using [gossip](http://telepathy.freedesktop.org/wiki/Gossip).
The UI is very clean and feature is quite handy. On ubuntu, you could just run `$ apt-get install telepathy-gnome`. If you want msn support, you may need the `telepathy-butterfly` module.  Here is a shot of [conversation window](http://linuxfire.com.cn/~alecs/pics/gossip-telepathy.png). And this shot shows the [calendar-based log window](http://linuxfire.com.cn/~alecs/pics/gossip-log.png). And btw, it also has tray notification with sound alert. Quite like gtalk on windoze.

2. [Liferea](http://liferea.sourceforge.net/).  Reading rss/blogs is a common daily task.  I used to use the [Sage extension](http://sage.mozdev.org/) for firefox. But liferea's look and feature are more attractive and nice. Here is a shot showing the [main interface](http://linuxfire.com.cn/~alecs/pics/liferea.png).

3. [Gnome Launch Box](http://developer.imendio.com/projects/gnome-launch-box).
It can let you quickly search and find desktop apps and/or bookmarks.
Once installed, config the hotkey[1] and run in the transparent mode `$ gnome-launch-box -t`. This is [how it looks](http://linuxfire.com.cn/~alecs/pics/gnome-launch-box.png).  Use your configed hotkey to activate it.

4. [Affinity-search](http://code.google.com/p/affinity-search/), by the same author of avant. It can search not only the apps but all the files and other stuff. Ubuntu now does not have it in the repo.  You can get it from the [same repo](http://awn.wetpaint.com/page/Ubuntu) of avant. This is the default [main window](http://linuxfire.com.cn/~alecs/pics/affinity-main.png) and here is a [shot of search](http://linuxfire.com.cn/~alecs/pics/affinity-search.png).

5. [Some avant plugins](http://awn.wetpaint.com/page/Dbus+Plugins).


[1] You can only set it from gconf-editor, which i totally hate.  I think gconf-edit is totally a bad idea.  It's starting to become windoze registry for gnome. And whats worse, more and more apps are following this way.  'Less is more'.  But dont be too less.  

And btw, congrats to Ubuntu team. Feisty fawn is officially released.  Will upgrade to Gusty Gibbon once the testing branch is accessible.  Oh, i made up a code name for the next HH release:  Healthy Hallows.  

PS, somebody recommended a M$ font to me, you can [take a look](http://linuxfire.com.cn/~alecs/pics/msyh.png).

