---
layout: post
title: Various ACMs
time: "00:59"
extended: ":EXTENDED:"
---

A productive day.

New members joined in working on ACM together.

Besides, i myself have submitted 4 problems. All are easy ones:

<a href=http://linuxfire.dhis.org/~alecs/code/hanoi.c>Hanoi Troubles Again</a>, <a href=http://linuxfire.dhis.org/~alecs/code/random.c>Pseudo-Random Numbers</a>, <a href=http://linuxfire.dhis.org/~alecs/code/reverse.c>Reverse Text</a> and <a href=http://linuxfire.dhis.org/~alecs/code/sumbig.c>Integer Inquiry</a>.

The last one is also about dealing with big numbers (addition arithmetic).
Something you should pay attention to: 

1) Allocate _enough_ memory (100 100-digits numbers addition would occupy at most 102 digits).
2) For big numbers, dont forget 0 + 0 is also 0. (Duh!?)


Today's Tips:
1) Dont be cheap about your memory. LIMIT + 1 does not suffice.
2) Be careful, be MORE careful.
3) Test against the extreme cases.

Avoid those off-by-one bugs!

<b><i>Update</i></b>:

Although it has passed the online judge, there was a bug in the old version of sumbig.c (Integer Inquiry). reverse() has not correctly dealt with odd-digits number. Thanks for Penguin (aka. walte) triggering this bug.

New version uploaded.

