---
layout: post
title: Million Digits of E, Sqrt(2), Pi
time: "17:12"
extended: ":EXTENDED:"
---

> More puzzles, more fun.

Besides [acm oj](http://acm.tju.edu.cn/toj/ranklist.html) and [projecteuler](http://projecteuler.net), i also like to solve the puzzles on [spoj](http://spoj.pl). The ACM/ICPC rules are rather limited -- you have to submit the src code (only one file) in java or c/c++.  ProjectEuler is much more free: it just accepts the final answer -- you are free to use any tools/langs as you like.  Spoj stands kinda in between: it still accepts a one-file-src but you can use a lot of languages (just to name a few: bash, perl, lua, lisp,  python, haskell, c, asm, etc.). In other words, it's hard to not to find your favorite language there.  But you cannot use any external src or libs (only standard feature or lib of the langauge is allowed).

Among many interesteting puzzles, spoj has some [challenge problems](http://www.spoj.pl/problems/challenge/).  These problems are not simply checked right-or-wrong. Instead it makes the rank based on its problem-specific scoring: usually precision, sometimes code-length.  Take the following three for example:

* [Digits of e](http://www.spoj.pl/problems/EVAL/)
* [Digits of sqrt(2)](http://www.spoj.pl/problems/SQRT2/)
* [Digits of pi](http://www.spoj.pl/problems/PIVAL/)

The rules are same: given limited time and code-length, calculate the value in as many decimal digits as possible.

All three problems involve arbitrary-precision computations -- you either implement your own FFT or use those languages that have bignum built in (like java, python or haskell). 

* Digits of e -- just use the Taylor expansion with Binary-Splitting.
* Digits of sqrt(2) -- Newton iteration (note that each iteration doubles the precision).
* Digits of pi -- use Chudnovsky series with Binary-Splitting.

For the underlying magic algorithms, see the those wonderful [papers/docs](
http://numbers.computation.free.fr/Constants/constants.html).  Here's a reference implementation for [pi digits using gmp](http://gmplib.org/pi-with-gmp.html) -- claims to be the world's fastest -- for as many as billion digits.  Also, [mpmath](http://code.google.com/p/mpmath) has some interesting implementations as well.

I myself dont bother to implement a FFT in c/c++ (and i doubt i could write a fast enough version in 4K code). Python is really slow for this (sorry, sad, but true) . Haskell's Integer is using the fast(est) [gmp](http://gmplib.org).  Not only it's fast, it's very convenient and leads to (much) shorter and cleaner code. You can [see](http://www.spoj.pl/ranks/EVAL/) [the](http://www.spoj.pl/ranks/SQRT2/) [ranks](http://www.spoj.pl/ranks/PIVAL/).  Also specific ranks in your [favorite](http://www.spoj.pl/ranks/EVAL/lang=PYTH) [languages](http://www.spoj.pl/ranks/PIVAL/lang=HASK).

Other interesting ones might be:

* [Make the src as short as possible](http://www.spoj.pl/problems/SIZECON). Perl is the ruler for this. But you can try to be the top 1 on a specific language ranking.
* [Compress and uncompress in one file](http://www.spoj.pl/problems/MAGIC2/). The hard part is how to dump the compressed data in src file.
* [Magic Markov](https://www.spoj.pl/problems/MAR/). Write code to generate code, with special craft.


