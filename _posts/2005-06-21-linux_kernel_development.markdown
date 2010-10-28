---
layout: post
title: Linux Kernel Development
time: "16:32"
extended: ":EXTENDED:"
---

Did a kinda quick reading of <a href=http://www.amazon.com/exec/obidos/tg/detail/-/0672325128/ref=pd_sxp_f/103-0826389-0675856?v=glance&s=books>this book</a> last week.

Modern OS kernels tend to become much more feature-rich(and thus complicated) than ever before.  Many aspiring programmers want to get their feet wet but dont know how/where to start.  Many books on the OS thoery and some books on detailed kernel snippet. But never a book was like <a href=http://rlove.org/>Robert Love</a>'s.

Get-to-the-point & humorous writing style, Robert leads you to every corner of the kernel, process, memory, file system, etc., with his concise and sharp insights.  Well, i personally really like the process scheduler and the kernel sync part.  This book tells you what's what in the kernel and many new exciting features brought in since 2.6.  It expains how to utilitize various facilities provided by kernel and many kernel APIs (ie. rwlock, slab allocator. etc.). 

This book is written so well that it exactly meets the intent of the creation of the book in the first place: make more people easily get involved in the kernel development.

Anyway, i mainly did a rough skim except some parts i'm most interested in.
I bet i'll read it back and forth (ie. for references or deeper understanding) later. 

Okay, now lets finish this blog entry with a <a href=http://linuxfire.dhis.org/~alecs/code/pstree.c> trivial & nonsense module</a>. It works like pstree, which prints all the processes (but without pstree's fancy ouput format). Well, actually, it just traverses the process tree in the pre-order.

Oh..one of the side-effects of reading this book is that i know compiling linux kernel is not _that_ frustrating (compared to fbsd) any more. The kbuild system introduced in 2.6 is quite good and eases the compiling (kernel & modules) process pretty much.

