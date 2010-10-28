---
layout: post
title: Haskell Platform
time: "19:33"
extended: ":EXTENDED:"
---

>The Haskell Platform is a blessed library and tool suite for Haskell distilled from Hackage, along with installers for a wide variety of systems. 

IOW, It's Haskell with Batteries Included.

ghc on jaunty is totally out of date.  I recommend you grab the latest bin from the [ghc official site](http://haskell.org/ghc).  After that, just install [Haskell Platform](http://hackage.haskell.org/platform/). It contains a variety of selected commonly [useful lib and tools](http://hackage.haskell.org/platform/contents.html). You just dont need to install (and set up) 'em one by one.

Just a note for jaunty: install libedit-dev (not libeditline-dev) if you got a dep error for editline.



