---
layout: post
title: Backtracking
time: "15:27"
extended: ":EXTENDED:"
---

Backtracking is one of the common algorithms that can be used in those enumeration problems without brute force.

It often comes with recursion and DFS (Depth First Search). Many classic problems like <a href=http://linuxfire.dhis.org/~alecs/code/queens.c>Eight Queens</a> and <a href=http://linuxfire.dhis.org/~alecs/code/subsum.c>Subset Sum</a> can be solved using backtracking techniques.


Problem I 

<a href=http://acm.zju.edu.cn/show_problem.php?pid=1003>ACM: Crashing Balloon</a>

Your main job is to facotrize these 2 numbers without using same factors. It's not practical to compute all possible factors solutions for each number and check if there's any overlap. Not surpringly, we can apply the backtracking method here. We DFS until we get a statisfactory factors solution. <a href=http://linuxfire.dhis.org/~alecs/code/ballon.c> A working code here</a>.


Problem II

Generate a (m + n) length string consisting of m 'A's and n 'B's.  

1) How many different strings would be generated?
2) Print out all these different srings.
3) Assuming we make up each sting sequentially from its first character to its last, compute each string's generating possibility.

Solution:
1) C(m + n, m).  That is, we choose m locations from (m + n) locations to store 'A' (and the left n locations for 'B').

2,3) For each step of composing a string, unless there're already m 'A's or n 'B's, we can choose either 'A' or 'B' (each 50% possibility for this step). If there're already m 'A's, then we can only choose 'B' (100% possibility). Likewise, we can only choose 'A' (100%) if all 'B's have been chosen.

Hint: Think about a binary tree, each node of which has a left child 'A' and/or a right child 'B'.

<a href=http://linuxfire.dhis.org/~alecs/code/combposb.c>This working code</a> DFSes for 'A' and then backtracks to 'B'.


Only by enough practicing and thorough thinking can we really master and corretly apply this algorithm. Whatsoever, programming is by means of thinking, reading and writing (also debugging? =).

