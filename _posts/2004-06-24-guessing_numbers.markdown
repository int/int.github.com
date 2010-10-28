---
layout: post
title: Guessing numbers.
time: "02:22"
extended: ":EXTENDED:"
---

This is an interesting game. Jane chooses a random number (composed of four different digits from [0-9]) and gives John 10 chances to guess what the number is. Each time John provides a possible answer, Jane gives back a hint AB, of which A indicates how many rite digits with rite position there are in the answer that John just provided and B indicates the number of digits that are rite but not at the rite position.

e.g. Jane chooses the number '9205'.
John: 1234
Jane: 01
John: 5678
Jane: 01
John: 4387
Jane: 00
John: 9026
Jane: 12
John: 2095
Jane: 13
John: 9205
Jane; 40


John is a computer geek so he wants to write a program to figure out the rite number.

How would he code it? and how would you?
There may be a dozen of ways to do it. One of the most intuitive is kinda like how you brutely-crack password (remember? =). 

An-easy-to-understand-and-simple-to-implement-but-maybe-not-the-perfect-algorithm:

1) Randomly pick up a number from possibilities (5040 possibilities in start).
2) Compute each possibilities' AB against the picked number. 
3) Comparing with the hint, scale down the possibilies (whose AB == hint). 
4) Repeat the steps above until there is only one possibility left.


Actual code always explains better than mere words. Here's a working <a href=http://linuxfire.com.cn/~alecs/code/guess.c>sample</a>. Even in the worst case, it can get the rite anwser after 7 guessings: (5040/1440)^7 == 6433. Enjoy.
