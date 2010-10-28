---
layout: post
title: "Cabal and Cabal-install"
time: "16:26"
extended: ":EXTENDED:"
---

[Cabal](http://www.haskell.org/cabal/) is a system for building and packaging Haskell libraries and programs.  Put it another way: its Setup.lhs is like Makefile.pl for perl or setup.py for python.  Well, you've got the idea.  See the [user guide](http://www.haskell.org/cabal/release/latest/doc/users-guide/) for details.

And [cabal-install](http://hackage.haskell.org/trac/hackage/wiki/CabalInstall) is like perl's cpan (the command) which can automatically download/install/update haskell package off from [Hackages](http://hackage.haskell.org/).  It's still a work in process.  Occasionally it cant resolve the dep right or miss out one or two packages. You might have to manually install them.  So be warned.

BTW, I dont think many ppl are still using the 'cpan' cmd to install perl modules these days.  At least not for most linux distros.  CPAN perl modules are very mature and most distro vendors have made their own pkg/ports already for you.  But not for haskell, because far few ppl are using/developing haskell pkg.  Either there are no pkg built or if there is, the pkg is usually outdated.  So if you need to install cutting-edge haskell pkg, i recommend cabal-install.  I used it to install [lambdabot](http://www.haskell.org/haskellwiki/Lambdabot).  Almost went fine except a dead dep loop. Manually fixed it anyway.


