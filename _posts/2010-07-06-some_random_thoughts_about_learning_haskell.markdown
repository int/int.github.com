---
layout: post
title: Some Random Thoughts About Learning Haskell
time: "15:48"
extended: ":EXTENDED:"
---

Learning Haskell is fun, fun, fun. In the process, you become more 'functional' (duh). You gradually tend to think in abstract and high-level. You end up writing more elegant and clear code (not just Haskell code, may it be python or c++, no kidding).  You may also find it [addictive](http://www.reddit.com/r/haskell/comments/cg8o5/haskell_is_addictive/) (functional alcoholic, hah).  But Haskell is well-known for the [steep learning curve](http://www.haskell.org/haskellwiki/Humor/LearningCurve).

Yes indeed, Haskell is hard to learn, *especially* if you have experience of imperative programming languages. Actually, the rumour goes that Haskell is easier to learn if your brain hasn't been conditioned by years of imperative programming. So here are some *casual* advice i'd like to share about how to make it smoother to learn haskell for those from imperative backgrounds:

1. **Unlearn and free yourself to embrace a new world**.  Take a deep breath and forget all those idiom/design-pattern/concepts/OO-coolness in your old language.  Why? because "class is not class, instance is not instance, function is not function, return is not return, blah is not blah any more". 

2. **Have a feel of it before getting too serious**.  Since haskell is so different, you are not supposed to grasp it like you did for 'yet another' imperative language. Relax yourself, play around a bit, find new cool things and make some mistakes. 

3. **Know your types**. Haskell is about types. It has a very powerful type system. If you get right about the underlying types, you are 99% close to compiling your code.  If you compile your code successfully, big chances are that the code will run correctly as expected.

4. **Welcome functions, the first-class citizen**. Though it may not the same but you can use function as you did variables in your favorite imperative language. Functions are everywhere. Everything is a function. Function's augments might also be functions (most cases are) and yet it returns a new function.  For instance, a -> b -> c -> d is actually a -> (b -> c -> d) while a may be of type (e -> f -> g).

5. **Never give up but often look back**. If you come from an imperative background, new concepts may seem overwhelming 'in the way'.  Some really depends on one another. If you want to understand this, you have to understand that and that. For example, to understand monad, you really have to understand how to use typeclass.

6. **Get your hands/feet dirty early on**.  Try reading haskell code and writing your own. Test your learnings by solving a math/algorithmic problem ([PE][1] and [spoj][2] are good places to go) or making some simple haskell scripts for your daily admin work. After that, you can try something bigger like [hackage][6] (or searching haskell on [github][5]).

Me myself still a newbie enjoys the learning process. The Haskell community is by far one of the most helpful and friendly communities i've ever met. You can subscribe to the Haskell-cafe and Haksell-beginners [mailing lists][3] or hang around @ [#haskell on freenode](http://www.haskell.org/haskellwiki/IRC_channel).

So good luck in your haskell study and haskell-fu practice. :^)

[1]: http://projecteuler.net
[2]: http://spoj.pl
[3]: http://www.haskell.org/haskellwiki/Mailing_Lists
[5]: http://github.com
[6]: http://hackage.haskell.org

