---
layout: post
title: "Last non-zero digit of N! (N factorial)."
time: "02:18"
extended: ":EXTENDED:"
---

ACM again =)

Problem: <a href=http://acm.zju.edu.cn/show_problem.php?pid=1222>Find out the last non-zero digit of N!</a>.

Solution:

Read <a href=http://www.mathpages.com/home/kmath489.htm>this paper</a> first.

You're supposed to understand the paper now or you can stop reading on this blog, period.

Method: change the number to 5-base and then look up the table as the paper suggests.

Here is <a href=http://linuxfire.dhis.org/~alecs/code/last.c>the code</a> showing the algorithm: base changing and table looking up. But you'd get a 'WA' if you submitted it. Why? Cos the input can be a very large number (ie. 10^100). Apparently a 'long long' number used in the code above cannot deal with it correctly. 

Remember how to deal with big numbers when you were in your data structure class? Save them in arrays, one index one digit.

Our problem here is to change a big 10-base number to 5-base. In fact, the only computation to the big number is to divide 5. Quite easy.

Here's <a href=http://linuxfire.dhis.org/~alecs/code/biglast.c>the final code</a>, enjoy.


PS, had submitted another 2 simple ACMs also: <a href=http://linuxfire.dhis.org/~alecs/code/html.c>the HTML</a> and <a href=http://linuxfire.dhis.org/~alecs/code/mod.c>2^x mod n = 1</a>


Got several off-by-one bugs. Should have been more careful. :-/

