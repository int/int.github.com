---
layout: post
title: Beautiful Dancing Links
---

> If you are going to walk on thin ice,  
> you may as well dance.

[Dancing Links](http://en.wikipedia.org/wiki/Dancing_Links) (DLX) is a
technique suggested by
[Knuth](http://www-cs-faculty.stanford.edu/~uno/papers/dancing-color.ps.gz) for
solving [Exact Cover](http://en.wikipedia.org/wiki/Exact_cover) problem.
Details are in the paper.  Here I just give some _outlines_ of DLX and how we
can apply it to solve problems.

The exact cover problem is to find a set of rows from a 0-1 matrix s.t. each
column has _exactly_ one 1.  A common backtracking method is suggested by Knuth
called the [Algorithm X](http://en.wikipedia.org/wiki/Algorithm_X).  Dancing
links is an fast implementation of Algorithm X utilizing circular doubly linked
links (hence the name DLX) taking the advantange that the more deeper we're at,
the more sparse the current matrix is.  It's fast in that it has fast
updating/restoring of the backtracking context.

Searching problems are hard to solve. Though there are optimizations and
pruning techniques available, they are very specific to the underlying problem
-- usually we cant easily apply 'em across problems.  Even for a specific
problem, it's not easy to predict whether a heuristic really works (well).  DLX
can be used to solve a range of exact-cover-like problems and often it has
reasonably good running time.  All we need is to build the matrix model --
normally we use rows to denote states and columns conditions.  And one
optimzation is that we always start searching the column that has the most 1s.

1. the classic exact cover problem.  Just build the matrix and run the DLX.
example: Sudoku.  Each row is a (r,c,d) state denoting that we put digit d to
position (r,c).  Three types of the sudoku rules are mapped to some columns of
the 01-matrix: each digit should appear once on each row, each column, and each
3x3 square. And also the condition that each position should be filled.  You
can try this method to solve a [16x16
sudoku](http://www.spoj.pl/problems/SUDOKU/).

2. loose cover problem: each column has _at most_ one 1. Example: N-Queens
Problem.  The nqueens problem is in fact a mixture of exact cover and loose
cover: every row and column has exactly one queen while every diagonal line has
at most 1 queen.  We can build and run the DLX as usual: only find the columns
of 01-matrix that are corresponding to the row/column of the nqueen rules. Try
solving this [nqueens](https://www.spoj.pl/submit/NQUEEN/) problem where some
queens are already on board. [1]

3. repeated cover problem: each column has _at least_ one 1. Example: minimum
dominating set on a bipartite.  We lose the row-exclusive-sweeping operation on
a column due to the 'at least' rule. But we can augment the DLX a bit to
justify this, and with a heuristic, it becomes an
[IDA*](http://en.wikipedia.org/wiki/IDA*).  The heuristic here is that at each
recursion level, we find the minimal number of rows we have to get to meet the
overall condition:

		mark all uncovered column untaken
		ret = 0
		for each untaken column:
			ret++
			for each row having this column:
				mark every column on this row taken
		return ret

Here's a [sample problem](http://acm.tju.edu.cn/toj/showp3608.html).

[1] Just note that you can also use the local search technique I mentioned in
these [blog](http://int.github.com/2006/04/05/8hn_queens_revisited.html)
[entries](http://int.github.com/2006/04/11/more_queens_more_random.html) --
when you go random, dont move those queens that are already on board.
