---
layout: post
title: Running Spaz on WebOS Emulator
time: "15:18"
extended: ":EXTENDED:"
---

> You got root, you got everything.

Yeah, Palm Pre is hot these days.  Now with the [webos emulator](http://www.geektang.com/2009/06/linuxwebos.html) and [ssh](http://www.geektang.com/2009/06/sshwebos.html) available, you can have more fun out of it.

Once you ssh to the emulator, you can see there's  `/usr/bin/ipkg`, by which you can list and install .ipk packages.

And all applications are in the `/usr/palm/applications` directory.  [Spaz](http://funkatron.com/spaz/) is a twitter client for webos and whats more, it's open source!  Just grab [spaz-webos](http://github.com/funkatron/spaz-webos/tree/master) and [spazcore](http://github.com/funkatron/spazcore/tree/master).  Put spaz-webos contents to `/usr/palm/applications/com.funkatron.app.spaz`  and spazcore contents to `/usr/palm/applications/com.funkatron.app.spaz/spazcore`.  

[some screenshots](http://linuxfire.com.cn/~alecs/pics/webos/)



