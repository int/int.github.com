---
layout: post
title: Crack the code
time: "02:36"
extended: ":EXTENDED:"
---

Just came cross <a href=http://acm.zju.edu.cn/show_problem.php?pid=1087>this interesting problelm</a> on <a href=http://acm.zju.edu.cn/>ZJU Online Judge</a>.

Basic solution:
1) determine the key length, and then,
2) determine the key.
 
<b>Method one</b>:

1) 'English' means the text is printable(spaces included). Assuming the key length is N (1 to 30), xor each possible key character in [a-z0-9] against every other N character of the shifted (from 0 to N-1) cipher. The resulted value shoule be printable. If N is the right key length, there must exist at least one key character that meets this 'printable' condition for each displacement. Since each key character is uniqe in the key and we are given enough long cipher, the smallest N is the key length.

2) With the right key length N, we calculate those right key characters as above. If we are lucky enough, there's only one character for each displacement. Thus we get the right key. If we are not so lucky, remember each key character should be exclusive with each other. Thus we _could_ get the right key.

Again, code explains better than mere words. Here's <a href=http://linuxfire.com.cn/~alecs/code/crack.old.c>the code </a>representing this method.

You can generate a cipher and then test the code. And you may find that there're some times that it cant determine the key.

Why? You may ask. Cause we havent used the 'English' condition as that much. As what much? You may then ask. 

'English' means it's English... Duh!  It's not only printable but should be composed of English words and have human-readable meanings.

Indeed. When you cant determine the key with the code above, there are only several keys possible (-DVERBOSE). You can xor these keys with the cipher text, read the ouputs and see which is English and which is not. This way you can find the right key.

Any better ways? You finally ask.
Yes.
<b>Method Two</b>:

1) Compare the cipher with itself shifted N bytes. If N is the right key length, there should be at round 6% equal bytes. If not, the rate is less than 0.4%. The smallest N is the right answer. [1]

2) With this right key length N, we try all possible key characters and calculate the English character frequencies in the 'plain' text. If the key character is right, then the frequencies should be like <a href=http://rinkworks.com/words/letterfreq.shtml>this</a>.

A working code <a href=http://linuxfire.com.cn/~alecs/code/crack.c>here</a>.

Since the given cipher is long enough, i have used a rather simplified method in the code: test if coincidence rate > 5.5% and only calculate the letter 'e' frequency and see if it's > 9%. (These 2 number are selected after a few tests.) In fact, to be more precise, you can calculate each coincidence probability to find which one is closest to 6% (using fabs() libroutine) and calculate all the 26 English characters' frequencies to get the right answer that's closest to real life.

Interestingly, we can see method 2 ues the 'English' condition so heavily and extensively that if you try a plain text that's composed of random characters or a c source code, you are not supposed to find the key.

For random characters, maybe we can combine these 2 methods. [2]

[1] Bruce Schneier, in his <b><i>Applied Cryptography</i></b> Section 1.4, introduces a method using <a href=http://raphael.math.uic.edu/~jeremy/crypt/coincidence.html>index of coincidence</a> to determine key length. 

[2] If the text is random, and the different letters are chosen with equal probability, the probability of a coincidence is much smaller (around 3.8 percent).
