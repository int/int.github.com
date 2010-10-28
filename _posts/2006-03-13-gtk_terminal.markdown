---
layout: post
title: GTK Terminal
time: "19:17"
extended: ":EXTENDED:"
---

mlterm recently performs really bad when outputting antialiased fonts and it
gets even worse under -ck.  I mean it's way too slow (invocation is fast; but
aa output is unbearable).

mlterm outputting aa texts under 2.6.15-ck7:

	$ time ls repo/git
	...
	real    0m6.104s
	user    0m0.007s
	sys     0m0.008s

	$ ls repo/git|wc -l
	439

As you can see there are only 439 entries but the output speed is far from
satisfactory.

As [A Look at GNOME 2.14](http://www.gnome.org/~davyd/gnome-2-14/)
suggests, gnome-terminal (vte based) beats
xterm by a factor of ten!  But i dont have those gnome libs and i tend not to
bloat my system. So i grab the latest
[vte](ftp://ftp.gnome.org/pub/GNOME/sources/vte/) and a terminal using
vte and gtk simply called
[gtk-terminal](http://developer.berlios.de/projects/gtk-terminal/).

Now the speed is very fast:

	$ time ls repo/git
	...
	real    0m0.033s
	user    0m0.004s
	sys     0m0.006s

Wow, it's impressive.

But there are some glitches out there that feel kinda annoying:

1. It does not acknowledge my font.conf (in which i disabled antialiase of my
Chinese font if it's small enough).

2. When highlighting text, it uses a light gray background to show the
result, which
is unacceptable since i use black background with foreground white fonts.
A sane behavior (like any sane terminal would do) is to reverse all the
colors when doing the highlighting.

3. It does not acknowledge the charset settings saved in '.gtk-terminalrc'. You
have to re-set it every time you use it.  Obviously it shouldnt be this way.


After digging around the gtk-terminal source code and
[vte reference](http://developer.gnome.org/doc/API/2.0/vte/vteterminal.html)
(it's kinda outdated; refer to the doc inside latest vte
tarball please), i found the problems were caused by:

1. It was enforced to always show antialiased text ignoring user settings.

2. The highlighting color was hard coded. (the default is actually
   to reverse colors if you dont hard code it)

3. The read-from-rc charset was overwritten with a 'default charset'.


The [resulting patch](http://linuxfire.com.cn/~alecs/patch/gtk-terminal.patch)
(against gtk-terminal version 0.2.1)
is in fact quite straightforward and self-contained.  You can get a clue
just by taking a look at it.

'Bugs' are fixed.  The world is clear.  And yet there are some
'features' i'd like to request/have (or code) later if possible:

1. Faster invocation.
2. Dynamic window title (of the running program).
3. Multi tabs. 

Would dig into it more.  Stay tuned.


