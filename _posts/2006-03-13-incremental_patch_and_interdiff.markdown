---
layout: post
title: Incremental Patch and Interdiff
time: "14:34"
extended: ":EXTENDED:"
---

ck always releases a full patch to major kernel version (like -stable kernel
patches do).  But kernel.org does provide incremental patch.  And since ck
refuses to use git to manage his tree (quilt, the small tool suits better
for his small project, he says), whenever a new ck patch is out, you have to
reverse the last patch (ie. 2.6.15-ck6) to the major version (ie. 2.6.15) and
then apply the new patch (ie. 2.6.15-ck7).  Sometimes a new ck patch just
modifies very few files (Makefile to change its version and one or two small
changes to a file or two).  So it would be better if there's an incremental
ck patch.  This way there will be less compiling (since less file changed)
assuming you dont do a 'make clean' every time you compile a new kernel.

Though you can view ck's ChangeLog and use quilt manually deleting/adding
single patches, that needs extra work.

Searched a while and found a package called
[patchutils](http://cyberelk.net/tim/patchutils/),
in which there's a slick program 'interdiff' that can
make incremental patch from two same originated patches.  Put it another way,
we can get the patch B->C from the patch A->B and A->C.  It does support the
`-p` option like the command `patch`. So to get a ck6->ck7 incremental patch,
we can use the following command:

	$ interdiff -p1 patch-2.6.15-ck6 patch-2.6.15-ck7 >ck6-ck7

Oh dude, thats kool.


