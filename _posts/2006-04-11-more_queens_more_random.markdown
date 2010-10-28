---
layout: post
title: More Queens, More Random
time: "14:48"
extended: ":EXTENDED:"
---

Lets dig into this n-queens problem more deeply.  What would it be when n is
getting _very_ large?

In [last entry](archives/2006/04/05/T22_19_47/index.html),
a poly-algo is used for n sized up about to 300.
That code is O(n^2)
time complexity.  Now lets imagine n can be very large, like 10,000, 100,000
or even 1,000,000.  The algo would not scale very well.

The same author of the last paper
proposed an [almost-linear
algorithm](http://www.cit.gu.edu.au/~sosic/papers/ieeekde94.ps.Z).
Here is the
[resulting code](http://linuxfire.com.cn/~alecs/code/nqueens_fast.c)
adapted.  As you can see, the content has not changed much
from [last code](http://linuxfire.com.cn/~alecs/code/nqueens.c).
The main difference is, in the old code we
systematically check each and every pair of queens whereas in the new code
pairs are chosen rather randomly. But the result changes dramatically.

`Talk is cheap; show me the numbers!`

	$ time (echo 1; echo 30000) |./old >/dev/null

	real    1m11.808s
	user    1m8.447s
	sys     0m0.579s

	$ time (echo 1; echo 30000) |./new >/dev/null

	real    0m0.436s
	user    0m0.422s
	sys     0m0.004s

And lets run an extreme case: 1,000,000.  The old code may take way too long.
But the new code:

	$ time (echo 1; echo 1000000) |./new >/dev/null

	real    0m31.707s
	user    0m30.089s
	sys     0m0.300s

Way kool.


