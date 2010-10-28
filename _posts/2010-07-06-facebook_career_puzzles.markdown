---
layout: post
title: FaceBook Career Puzzles
time: "15:02"
extended: ":EXTENDED:"
---

[Facebook career puzzles](http://www.facebook.com/careers/puzzles.php) is a collection of algorithmic fun problems.  You can solve it using a variety of programming languages. 

The rule is simple: you email your solution to the puzzle bot and it'll run your code and mail you back the result. If you pass all the test cases in the time/space constraint, you get a "congrats" reply telling you the time spent for running the longest test case. If you get it wrong, the bot just tells you failed but no details as to what/how/why (you dunno know it's timeout or wrong answer, etc.). And to prevent spamming the bot as a debug tool, the bot only replies every 4 hours.

The problems are of different hardness levels.  In fact, except some [thrift][1] problems, all are classic algorithm problems. Without disclosing too much to spoil the fun, i list some of 'em (but not to say which to which):

* Dynamic Programming (that's a fave for many contests; for several problems)
* [Max clique](http://en.wikipedia.org/wiki/Bron-Kerbosch_algorithm)
* [Stable Marriage](http://en.wikipedia.org/wiki/Stable_marriage_problem)
* TSP (you know it, classic. sometime an augmented TSP)
* [Kd-tree knn](http://en.wikipedia.org/wiki/Kd-tree)

This is an [unofficial FAQ](http://www.davideisenstat.com/fbpfaq/) you can refer to for more hints.


As of this writing, I solved all those 'classic' problems except some [thrift][1] problems. The thrift problems are really fun. They are a new style of interactive (dynamic) problems. Just that I have some problems (you know it) to connect to the [thrift server](http://thriftpuzzle.facebook.com/).

Those from ACM/ICPC background may find it annoying that there are no clear specification for input limit/range. I just give you a hint: If it's a NP-hard problem, the input could not be too big (in fact, it actually often is very small).

[1]: http://incubator.apache.org/thrift/

