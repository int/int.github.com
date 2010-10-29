---
layout: post
title: Old Way In New Era -- MT to Jekyll
---

My old MT blog is hosted at [linuxfire][fire], which is very slow to
access these days.  [MovableType][MT] is a good software.  I love it and I think it's the
best all-in-one blog suit and IMNSHO, way better than WordPress (WP).  MT has
all the stuff and features you need and works smoothly as you expected.  In
the same time, I'm a big fan of plain text and those simple-yet-power text
tools.  I like writing my blogs with my favorite editor.  Years back ago, I
even used the [nanoblogger][nb].  It's a static blog generator written in pure
shell scripts and commands.  It's kinda slow, though.

Nowadays, as we're in a post-cgi, web-richer-than-ever era, it seems static
generator is a new trend again.  Web apps are more mature and flexible these
days and it's way easier to hook up and glue 'em altogether. A static generator
fits well -- It's fast while you can seamlessly integrate different
applications.

Among many, [Jekyll][jekyll] is a modern and great blog-aware static
generator.  github makes all [pages][pages] automatically piped
through it.  Writing and updating blog works like a charm: `vim x.md && git
push`.  One of other interesting alternatives is [hyde][hyde], which is
written in python and more feature-rich.

The first step is to convert MT entries to [Markdown][md] format.  I used
[mt2jekyll][m2j] to convert my exported MT backup.  One thing to note is that,
in my exported backup, there are bogus duplicate separators which will confuse
the tool. So first use this [strip script][strip] to clean up and then use
`mt2jekyll` to do the conversion.

<script src="http://gist.github.com/651761.js?file=strip.pl"></script>

All entries have been successfully converted and the
markdown file have been rendered by Jekyll without any problems -- in fact,
very pretty. :-)  But I have problems to convert the comments.  So all old
comments are not showing up as of this writing.

Next, I spent some time to choose a site to fork (style, template, etc.) from
quite many [candidates][sites].  Some are really cool but I just end up with
the [original one][mojo] ([source][mojosrc]).  It looks clean and nice.  I
just tweaked a bit to make it mimic the Safari 5 Reader Mode look-and-feel.

Then, to make it more like a real blog 2.0, I added comment system [Disqus][dq]
and some social icons via [AddThis][add].

So this is it, as you can see, a simple and clean blog set up running on
github powered by Jekyll.  Missing features are nice-looking categories and
archives, tags, searches.  I might add them later as I get more familiar with
Jekyll and its template system to make more customizations.

You can get all my changes from [the src repo of this site][repo].  Once it's
set up, everything else becomes darn smooth-easy.  Hope I can write more and
more often -- sometimes I was really lazy to miss a lot of
should-be-jotted-downs about cool stuff or after-thoughts, which makes me feel
kinda regretted.

[md]: http://daringfireball.net/projects/markdown/
[jekyll]: http://github.com/mojombo/jekyll
[pages]: http://pages.github.com/
[repo]: http://github.com/int/int.github.com
[fire]: http://linuxfire.com.cn/~alecs/
[add]: http://www.addthis.com/
[sites]: http://github.com/mojombo/jekyll/wiki/Sites
[dq]: http://disqus.com/
[m2j]: http://github.com/metajack/mt2jekyll
[mojo]: http://tom.preston-werner.com/
[mojosrc]: http://github.com/mojombo/mojombo.github.com
[nb]: http://nanoblogger.sourceforge.net/
[hyde]: http://github.com/lakshmivyas/hyde
[MT]: http://movabletype.org
[strip]: http://gist.github.com/651761
