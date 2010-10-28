---
layout: post
title: Markdown'ed xml feeds and new MT theme
time: "18:27"
extended: ":EXTENDED:"
---

Markdown and MT are two of those things that the more you use it, the more you like it. 

But one thing annoying me so far is that the atom and rss feeds cannot be filtered and produced by markdown.  The entries in the feed are just plain raw (unmarkdown'ed) text.
We are not /.  I just want to make the feed contain well-formatted entries that one can
view in his/her favorite rss reader. 

I have tried to add `<MTMarkdownOptions>` tags but it did not work.  But finally there is a way to produce markdown'ed feeds: in the atom and rss MT templates, find and change `convert_breaks="0"` to `convert_breaks="1"`.

I have tested it and now both my [atom](http://linuxfire.com.cn/~alecs/mtblog/atom.xml) and [rss](http://linuxfire.com.cn/~alecs/mtblog/index.xml) feeds are containing markdown'ed formatted entries.

And just to cope with my recently rapid growing 'Desktop Mood', as you can see, i changed the MT theme to look more 'gnome-ish' aka  loose and clean.  The name is called [star crash](http://www.thestylearchive.com/designs/star_crash).   To use it with StyleCatcher, you have to do some [file rename](http://linuxfire.com.cn/~alecs/mtblog/2006/08/mt_styles.html).

