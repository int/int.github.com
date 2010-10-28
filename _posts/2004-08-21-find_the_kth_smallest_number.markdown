---
layout: post
title: Find the kth smallest number
time: "20:17"
extended: ":EXTENDED:"
---

Problem: Given N numbers, find the kth smallest number.

<b>Method 1):</b>
Sort all the N numbers, and then return the kth number.
<b>Method 2):</b>
While reading N numbers succesively,  maintain/update a list of k smallest numbers.

For large input, both of these two methods are not acceptable.

<b>Method 3): Quick select</b>
If you know how quick sort works, you'd have no problem understanding this quick select method. (Hint: Divide and Conquer.)

Basic algorithm:

1) Get a pivot in N numbers.
2) Partition these N numbers into 2 parts: those smaller than pivot (we note as S1) and those bigger than pivot (S2). S1 has |S1| numbers,  S2 has |S2| numbers.
3.1) if |S1| >= k, then the number we want is in S1. 
3.2) if |S1| == k - 1, then the number IS the pivot. Got it!!
3.3) else, it's in S2.

Recursively repeat the steps above until you've got the answer.

<a href=http://linuxfire.dhis.org/~alecs/code/qselect.c>Source code qselect</a>: always choose the first number as the pivot.  This is doing good for random input. But if the input is already sorted, it performs very bad.

So you may think, "why not randomly choose the pivot?".  Generating random number and modular computing are expensive operations. Instead, we just use a 'middle of three' approach. That is, choose the middle of the first, the middle, and the last number as the pivot. See <a href=http://linuxfire.dhis.org/~alecs/code/qselect2.c>Source code qselect2</a>.

PS, as for how to optimize quick select,

1) To be perfect for all cases of input, you can use the 'median of the median' method to choose the pivot. Divide N numbers to N/r groups (r is a small number like 5, or 9, etc.), get the median of each group: m1, m2, .. m(N/r).  And then choose the median of m1, m2, .. m(N/r) as the pivot.

2) When N scales to small values like 16, just use insertion sort to get the answer.

3) Write a non-recursive version. (Be careful!!)

Anyway, without these optimizations, our 'middle of three' recursive approach will be doing fine for almost all cases. =)

Not surprisingly, by changing a few lines, we can get <a href=http://linuxfire.dhis.org/~alecs/code/qsort.c>a version of qsort</a>.

