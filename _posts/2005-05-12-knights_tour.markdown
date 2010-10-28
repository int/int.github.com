---
layout: post
title: Knight's Tour
time: "03:59"
extended: ":EXTENDED:"
---

<a href=http://mathworld.wolfram.com/KnightsTour.html>The problem</a>:

Can a knight surf all the squares of a chessboard exactly by reaching one square for only once?

It's said that this problem was first proposed by Euler and then interested Gauss much. Well, we aint mathematicians. We just code.

Solution:

Warnsdorff's rule

This problem is in fact a special case of the Hamiltonian Path problem. A _plain_ backtracking is apparently not acceptable, as it would grow exponently. We need a _heuristic_ algorithm. Luckily (for us), Mr. Warnsdorff proposed one back in 1823.
The basic rule is that, at each step, we gotta move to the position from which we have fewest choices to move to other places. Sounds a little bit  confusing? Might feel better by just taking a look at <a href=http://linuxfire.com.cn/~alecs/code/knightour.c>the code</a>. It inputs a starting position and outputs one possible route.

If you do the math, for a 8 x 8 board, a knight can finish his tour from any starting square. <a href=http://linuxfire.com.cn/~alecs/code/knightour.test>Test my code</a> for this.  Here is <a href=http://linuxfire.com.cn/~alecs/code/knightour.out>the output</a>.

The most interesting part is maybe how to break the ties of the Warnsdorff rule. By carefully choosing a 'smart' order of directions, we can avoid any extra effort (too lucky!). But to get real, we maybe need to apply randomized algorithms and/or utilize the symmetric characteristics of the chessboard.
