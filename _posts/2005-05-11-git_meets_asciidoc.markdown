---
layout: post
title: git meets asciidoc
time: "17:39"
extended: ":EXTENDED:"
---

Linus' still on his vacation while other ppl continue on improving git.

As git has got to a point where the core itself is stable and mature eough, it's time for making some (great) documentation. One of the most  obvious advantages of open source is that, everyone can participate and contribue in various aspects of the project, be it coding, designing, art stuff, or documentation. And good documentation is as important as, if not more than, the code itself.

So here comes a wonderful text processing tool: <a href=http://www.methods.co.nz/asciidoc/>asciidoc</a>. 

Quick installation:

download, unpack, and then 

$ ln -s /path/to/unpacked/dir/asciidoc.py /somewhere/bin/asciidoc


AsciiDoc is good at converting plain text to a number of different formats like xhtml, html, docbook/xml, or docbook/sgml.

Basic usage:

$ asciidoc -b &lt;backend&gt; -d &lt;doctype&gt; &lt;filename&gt;
One of the nice features i like most is that asciidoc's docbook/xml backend works pretty well with xmlto/xsltproc[1] (well, it's designed to be so..).

ie.

$ asciidoc -b docbook -d manpage file.txt
$ xmlto man file.xml

or

$ asciidoc -b docbook -d article file.txt
$ xmlto -x xhtml.xsl xhtml-nochunks file.xml


Very neat, now it's easier to write docbook articles and/or books. =)
You can find more <a href=http://www.methods.co.nz/asciidoc/>examples</a> and <a href=http://www.methods.co.nz/asciidoc/userguide.html>docs</a> at asciidoc's web site.

See results in action: asciidoc generated[2] <a href=http://linuxfire.dhis.org/~alecs/doc/git.html>git manpages (html format)</a>. 


P.S, other news about git: Petr made up a 'core' git tree of his own: <a href=http://kernel.org/git/gitweb.cgi?p=cogito%2Fgit-pb.git;a=log>git-pb</a>, in which he would constantly apply newest patches from the git mailing list.


[1] xmlto is just a shell script wrapper to xsltproc.  Sometimes xmlto does not work so well; the asciidoc author directly uses xsltproc worldwide.

ie.

$ asciidoc -b docbook -d article file.txt
$ xsltproc --nonet chunked.xsl file.xml
or
$ xsltproc --nonet xhtml.xsl file.xml >nochunked.html

so main syntax to use xsltproc is like:
$ xsltproc --nonet &lt;xsl&gt; &lt;file&gt; [&gt;output]

[2] command:
$ asciidoc -b css-embedded -d manpage &lt;file&gt;
