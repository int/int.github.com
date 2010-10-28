---
layout: post
title: Cracking RSA for Fun and Profit
time: "17:18"
extended: ":EXTENDED:"
---

You may use RSA (or other public key crypt method) every day without even noticing it or actually bothering 'whats under the hood'.  But for one day, you might ask, "what's actually under the hood anyway?"

Recently I've been reading a new book about algorithms -- [Algorithms](http://www.cs.berkeley.edu/~vazirani/algorithms.html).  In the Chap 1 [Algorithms with numbers](http://www.cs.berkeley.edu/~vazirani/algorithms/chap1.pdf), the authors give a very good view of the underlying theory and smoothly outline the [elegant algorithm](http://en.wikipedia.org/wiki/RSA).  You never truly understand an algorithm until you get your feet^Whands wet and actually code a working implementation.

So here's a small [RSA skeleton](http://linuxfire.com.cn/~alecs/code/rsa.hs) implemented in haskell, which contains all bits including: Fermat's testing, getting random large primes, calculating mod inverse (extended-Euclid),  the cipher functions and a simple test.
Cracking RSA is actually very easy: just factorizing a very large number n = p * q (p, q are primes).   No, i'm kidding. It's very hard, as factorizing large numbers has no efficient algorithm (so far).  And it's actually what RSA's security comes from: you just cant easily (quickly) factorize a large number.

But what if the number is not so large?  There's an algorithm called [Pollard's rho heuristic](http://en.wikipedia.org/wiki/Pollard%27s_rho_algorithm).  It's a [Las Vegas algorithm](http://en.wikipedia.org/wiki/Las_Vegas_algorithm), which means the algorithm may never terminate (what??) but if it does, it's 100% correct.  In practice, the rho algorithm normally  runs in O(n^0.25) for a composite n.  Here's my [toy rho](http://linuxfire.com.cn/~alecs/code/rho.hs) implementation.

Just for fun, you can try cracking a [small-scale RSA](http://acm.pku.edu.cn/JudgeOnline/problem?id=2447) or testing your code against [this one](http://acm.pku.edu.cn/JudgeOnline/problem?id=1811).  The online judge has no haskell or python support, i instead used java for its [BigInteger class](http://java.sun.com/j2se/1.4.2/docs/api/java/math/BigInteger.html).  To avoid rho running into an infinite loop, you might do some extra work (primality test, steps limit, random iterate function, etc.). Java BigInteger has provided the isProbablePrime function.  To implement one, you can use the [Rabin-Miller algorithm](http://en.wikipedia.org/wiki/Miller-Rabin_primality_test). It's a [Monte Carlo algorithm](http://en.wikipedia.org/wiki/Monte_Carlo_method), which means it may not be 100% correct but the more time you run it, the more correct it is.

To have more fun, I encrypted the src code for the above two problems: [crack rsa](http://linuxfire.com.cn/~alecs/code/2447poj.secret.txt) and [prime test](http://linuxfire.com.cn/~alecs/code/1811poj.secret.txt).  Though the keys in the original problem are less than 2^64, to make it a little harder for you, i used a slightly larger key (2^91 ~ 2^92).  Try deciphering the secret code, given the public key as (5, 3136682460441793638416097209). :^)

PS, for algorithms, please never forget to refer to the book [CLRS](http://en.wikipedia.org/wiki/Introduction_to_Algorithms). Just FYI, the R in CLRS is also the R in RSA. =)  Chap 31 has wonderful materials about various number theory algorithms.
