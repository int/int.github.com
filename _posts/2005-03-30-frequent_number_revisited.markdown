---
layout: post
title: Frequent Number Revisited
time: "22:11"
extended: ":EXTENDED:"
---

Last year i <a href=http://linuxfire.dhis.org/~alecs/blog/archives/000016.html>blogged</a> an <a href=http://acm.zju.edu.cn/show_problem.php?pid=2132>interesting problem</a> about finding the most frequent number in limited memory. I used a kinda complex divide-and-conquer method at that time to solve it.

Occasionally today, i found a much more elegant algorithm for this problem when reading the book <a href=http://www.amazon.com/exec/obidos/tg/detail/-/9810237405/qid=1112191351/sr=1-1/ref=sr_1_1/103-2122093-0254262?v=glance&s=books><i>Algorithms Design Techniques and Analysis</i></a>.

The basic idea for this algo is:

<b>If two <i>different</i> elements in the original sequence are removed, then the majority (aka the most frequent number) remains the majority in the new sequence.</b>

So life becomes easier. We start by denoting the first element as the 'x', set a counter with value 1 for it, then scan the elements left one by one: 

If it's the same as the 'majority', then increase the counter by one; 
otherwise, decrease the counter by one.

After all elements are scaned, if the counter is greater than zero, then x is just the answer. What's most important is that, whenever counter gets to be zero, we assign the next element as the new 'x'.

So to the original problem, we can apply the method above with an on-line algo. <a href=http://linuxfire.dhis.org/~alecs/code/freq2132.c>Final code</a> runs in space O(1) and time O(n). Cheer for the power of algorithms. =)

