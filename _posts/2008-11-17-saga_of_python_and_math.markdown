---
layout: post
title: Saga of Python and Math
time: "14:29"
extended: ":EXTENDED:"
---

I've listed some [math tools and libraries](http://linuxfire.com.cn/~alecs/blog/2008/06/project-euler.html) before. A lot of math tools have their own DSL (domain-specific language) for quick & easy access to their various math functions with some primitive control flows.  DSL is better in the sense that it's relatively convenient and it gets hooked more tightly to the underlying base (i.e. shorter code, more inner-involving). A general programming language has its own strength: it's powerful, elegant, much more mature and more easy to access the 'outer' world.  DSL for the math tools (like the 3 big Ms) sometimes looks kinda awkward from a 'programming' point of view.  Besides, people tend to like doing work in their own favorite languages.

Python is rather popular nowadays. It's been used in various fields -- sys admin, net utility, web, prototyping, unit testing, etc.  -- and of course, in mathematics, science, and engineering. One of the well-known tool chains is: [scipy](http://www.scipy.org/) + [numpy](http://www.scipy.org/NumPy) + [matplotlib](http://matplotlib.sourceforge.net/) + [ipython](http://ipython.scipy.org/moin/) aka the [PyLab](http://www.scipy.org/PyLab).   scipy/numpy is tremendously good for numeric computation and matplotlib can generate high-quality [2D plots](http://matplotlib.sourceforge.net/gallery.html) -- in your [favorite language](http://matplotlib.sourceforge.net/examples/index.html).

Another tool chain i'd like to share is for symbolic manipulation: [gmpy](http://code.google.com/p/gmpy/)  + [mpmath](http://code.google.com/p/mpmath/) + [sympy](http://code.google.com/p/sympy/).  gmpy provides the python binding for [gmp](http://gmplib.org/), mpmath provides some high-level arbitrary-precision computing functions while sympy is really good at symbolic processing with great 2D/3D plotting support and a convenient interactive 'isympy'.  Your distro may have these pkgs but please check if they are outdated.  I recommend you use the latest version built from their [own](http://code.google.com/p/gmpy/source/checkout) [repos](http://git.sympy.org/?p=sympy.git).  (sympy has included mpmath, btw). Newer versions are way faster -- Try calculating 1M digits of Pi.

And here's a big all-in-one math tool called [sage](http://www.sagemath.org/), which is using python as the primary programming language and can be regarded as a free alternative to the 3 big Ms.

Also, two tools not specifically for math: [psyco](http://psyco.sourceforge.net/) and [parallel python](http://www.parallelpython.com/) (via [bones](http://li2z.cn/2008/11/09/parallel_python/)).  psyco is kind of a python JIT. If you do a lot of cpu-bound instructions in python, it is your lovely friend.  pp is for parallel computing (multi-core or even network cluster). It can split computation [at the function level](http://www.parallelpython.com/content/view/17/31/).

Finally, for speed-lovers, there's a language called [wirbel](http://mathias-kettner.de/wirbel.html). It has very similar syntax to python (almost equal). The key difference is that it can compile src to native bin, thus it's very fast. But limited: not all python code can be easily changed and compiled by it of course, at least not now.  Still an interesting alternative anyway.  You might want to have a look.


