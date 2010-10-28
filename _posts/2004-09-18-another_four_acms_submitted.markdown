---
layout: post
title: Another four ACMs submitted
time: "23:51"
extended: ":EXTENDED:"
---

Easy ones.

I) <a href=http://linuxfire.dhis.org/~alecs/code/nonstop.c>Nonstop Travel</a>

Be careful when the arriving time (in seconds) at a location is NOT integer.

II) <a href=http://linuxfire.dhis.org/~alecs/code/day.c>What day is it?</a>

Very interesting and infomative. You know what day Jan 1st 1 is? How many days are there in the month of September 1752?  (Hint: run 'cal' on your UN*X box).

Two useful links:

1) <a href=http://mathforum.org/library/drmath/view/62324.html>Zeller's  Rule</a>
2) <a href=http://users.aol.com/s6sj7gt/mikecal.htm>How about the a date</a>

Note that both of the 2 formulas above only apply to the Gregorian Rule. (A little bit change needed for the Julian Rule).

III) <a href=http://linuxfire.dhis.org/~alecs/code/tree.c>Is it a tree?</a>

Just remember each node except the root has exactly one parent, no more no less (as in real world, every one has only one father, duh!).

And dont forget those void trees (having 0 node).

PS, i've used hash table for looking up. You can use hsearch() when you are doing with strings. Well whenever for ingeter hashing, i'd go for <a href=http://www.concentric.net/~Ttwang/tech/inthash.htm>this hash function</a>.

IV) <a href=http://linuxfire.dhis.org/~alecs/code/parens.c>(Your)((Term)((Project)))</a>

Familiar problem. You know those parentheses gotta need a stack.

Have gone crazy about a off-by-one bug. Trials-and-Fails(WAs). Should have been calm enough. Should have done this problem ACed in 10 minutes.

