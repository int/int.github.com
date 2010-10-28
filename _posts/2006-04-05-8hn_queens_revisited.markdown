---
layout: post
title: 8^HN Queens Revisited
time: "22:19"
extended: ":EXTENDED:"
---

I once wrote
[a blog entry](http://linuxfire.dhis.org/~alecs/blog/archives/000018.html)
about 8 queens problem using backtrack. Backtrack is good for small n
generating _all_ solutions for n-queens problem.  But what if the n is getting
large?  It performs very bad, since it runs exponentially (try n = 27 for
[this code](http://linuxfire.com.cn/~alecs/code/queens.c)).

Here is an interesting problem [Who needs 8 Queens when you can have
N](http://acm.hit.edu.cn/ojs/show.php?Proid=2197&Contestid=0).  Note that we
are to find _one_ solution that satisfies the no-attacks requirements, not _all_
the solutions as a backtrack does.

Dont panic.  Read this paper: [A Polynomial Time Algorithm for the N-Queens
Problem](http://www.cit.gu.edu.au/~sosic/papers/sigart90.ps.Z).
Oh dude, it is AMAZING (read: power of algorithms).  In
short, it utilizes a randomized approach with gradient-based heuristic local
search.  For a random permutation, swap where there is a reduction of
attacking-conflicts.  Besides, there are also other good (small) tips.  It
really broadened my algo knowledge base and it's not only for this particular
n-queens problem but can be generalized for other searching problems. Kool.

Here is the
[final implementaion](http://linuxfire.com.cn/~alecs/code/nqueens.c)
according to this paper.  It runs
[very fast](http://acm.hit.edu.cn/ojs/status.php?Proid=2197&Contestid=0).


