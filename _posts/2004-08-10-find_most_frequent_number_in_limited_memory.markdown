---
layout: post
title: Find most frequent number in limited memory
time: "23:13"
extended: ":EXTENDED:"
---

ACM time again!. =-)

<a href=http://acm.zju.edu.cn/show_problem.php?pid=2132> The problem</a> itself is pretty straightfoward. There are L numbers and exists one number that has more than 2/L occurences. Your task is to find this most frequent number.

Sounds too simple?  "Why not just use the 'sort and then find' method?"

What really makes this problem difficult is that there can be as many as 250,000 32-bits integers but you only have 512k memory available. Lets do some math first. 250000 * 4 / 1000 == 1000k. Apparently it does not fit in the limited given memory. And you should remember that, besides the numbers themselves consuming memory, you'd also need other free memory for running stack, data section, and/or bss. 512k is ALL that you can consume, not just for storing the numbers.

So you're not expected to read all numbers just once, sort, and then find.  We have to intead read a portion of the numbers and do some calculation repeatedly until we've got the rite anwser.

<b>Base theory/math: </b>
We divide the L length into n portions, L1, L2, ..., Ln. The rite answer must be the most frequent number at least in one of these portions.

<pre>
  A1   A2   A3                  Ai                  An
|----|----|----|----|----|----|----|----|----|----|----|
  L1   L2   L3                  Li                  Ln
</pre>

<b>Each step: </b>
1) Find out the most frequent number Ai, if any, in the Li portion. 
2) While trying find A(i+1), we also record Ai's occruences Oi in L(i+i) and add Oi to  Ai's earlier occurences.

<b>So Finally: </b>
1) For each portion, if we've got an Ai, we've also got its occurences in the portion [Li + L(i+1) + ... + Ln] (we note as LENi). 

2) We test Ai from A1 to An, until its Oi > LENi / 2. And Ai is just the rite answer.

The last question may be, "how many portions do we choose?". Well, that depends. I use qsort to sort numbers and since qsort is a recursive function and thus would consume a lot of stack space for large input, i just divide 250,000 into 50 portions.  If you use an in-place non-recursive sort method, ie. insertion sort, maybe you'd need fewer portions. But be warned, insertion sort tends to be slower than qsort. So be sure your program wont get a 'TLE' error.

<a href=http://linuxfire.dhis.org/~alecs/code/freq.c>A not-so-good-but-anyway-working program here</a>.  (Runs 2.9 secs, consumes about 420k mem).  Really not so good. Some guy using Pascal just worked out to use 56k mem in less than 1 sec! Beats me! Tell me if you have better solutions.

<b><i>Update</b></i>
Just wrote <a href=http://linuxfire.dhis.org/~alecs/code/freq.tree.c>another version</a> with no sorting needed (using binary search tree, instead.) This version requires about same mem as the old one but runs faster (1.4s).

And <a href=http://linuxfire.dhis.org/~alecs/code/freq.tree2.c>here a new version</a> using non-recursive tree routines. Performs slightly better (1.2s). The reason why it does not gain much against the recursive version is because there's no repeated/redundant computing in the recurive version. Anyway, this new version is, at least, less ugly. :^)

<i><b>Update:</b></i> More elegant algo found and <a href=http://linuxfire.dhis.org/~alecs/blog/archives/000028.html>blogged in another entry</a>.

