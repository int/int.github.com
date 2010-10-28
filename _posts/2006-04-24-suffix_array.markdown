---
layout: post
title: Suffix Array
time: "17:02"
extended: ":EXTENDED:"
---

suffix tree and suffix array are good at full-text search.  The
underlying property they utilize is very simple (yet elegant & powerful):
Any substring of a given string must be the prefix of one of suffix
strings of the original string.

There are really
[many](http://www2.toki.or.id/book/AlgDesignManual/BOOK/BOOK3/NODE131.HTM)
[many](http://www.csse.monash.edu.au/~lloyd/tildeAlgDS/Tree/Suffix/)
[many](http://www.dogma.net/markn/articles/suffixt/suffixt.htm)
[many](http://www.cs.dartmouth.edu/~doug/sarray/)
docs/papers/codes concerning these two structures
and their applications.  In short, suffix tree is easy to understand and since
it has an explicit tree structure, it's easier to apply.  But it consumes more
space than the suffix array and is nontrivial to construct quickly (linear
time).  The suffix array on the other hand is more compact but it's still not
very easy to construct in linear time.  Some algorithms just first build the
corresponding suffix tree and then do a traverse to build the resulting array.

Recently there's a new algorithm that uses a 'difference cover' approach
(divide & conquer wrt modular to 3) to construct the array in linear time.
See the paper [Linear Work Suffix Array
Construction](http://www.cs.helsinki.fi/u/tpkarkka/publications/jacm05-revised.pdf).
Among other Good Things (tm), it elegantly utilize recursion,
radix/counting sort and various index reference tricks.
Another good reference is about how to get the lcp (largest common prefix)
from a built suffix array in linear time: [Linear-Time Longest-Common-Prefix
Computation in Suffix Arrays and Its
Applications](http://www.inf.fu-berlin.de/inst/ag-bio/FILES/ROOT/Teaching/Lectures/WS0506//WeiterfThemenBioinf/papers/LinearTimeLCPComputation-KasaiLeeArimuraArikawaPark-CPM01.pdf).

[This problem](http://acm.pku.cn/JudgeOnline/problem?id=2774)
is just to compute the longest common substring, which can be
beautifully solved using the suffix array and lcp algorithm mentioned above.
Here is the [final code](http://linuxfire.com.cn/~alecs/code/sa2774.c).

Oh lets end this blog with a poem praising the magic structure 'tree' (though
here we didnt use it but an array, the tree structure is really 'magic' and
thus deserves such kind of praise.)

>I think that I shall never see  
>A poem lovely as a tree.  
>Poems are made by fools like me,  
>But only God can make a tree.  


