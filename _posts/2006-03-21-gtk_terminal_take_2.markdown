---
layout: post
title: Gtk Terminal (Take 2)
time: "16:25"
extended: ":EXTENDED:"
---

The default width of gtk-terminal is 80 columns.  But since the scroll bar
itself occupies one column, there are only 79 cols left for text, ie. make
menuconfig would complain about it.

This is really a quick-and-dirty fix.  I hard coded it in the source code.
It'd be better if we make it a option and read it from the config file.  But
heck, 'Laziness is the top 1 nature of programmers'.  Here is the
[resulting
patch](http://linuxfire.com.cn/~alecs/patch/gtk-terminal-take2.patch)
(which contains all the previous changes).  The new change is
actually that added set_size line.


