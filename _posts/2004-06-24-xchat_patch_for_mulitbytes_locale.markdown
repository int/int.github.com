---
layout: post
title: xchat patch for mulitbytes locale
time: "00:47"
extended: ":EXTENDED:"
---

Xchat is using utf-8 as much as possible in itself. There is a problem when printing texts that's neither utf-8 nor iso-8859-1 (ie. a zh_CN.GBK encoded file on zh_CN.GBK locale). The texts cannot be properly shown in the running xchat on localhost (other clients who have recieved the texts can see them without problems anyway). 

So i got my feet wet and tried to write a workable patch. <a href=http://forum.xchat.org/viewtopic.php?t=118&sid=daa915323582dc349a8e7a1dc91bf331>This</a> is how it was going with the discussion of xchat author Peter Zelezny.

And the final patch can be downloaded <a href=http://linuxfire.dhis.org/~alecs/patch/xchat.patch>here</a>.

That said, use utf-8 wherever possible. When writing scripts  for xchat, better save them in utf-8 encoding.

