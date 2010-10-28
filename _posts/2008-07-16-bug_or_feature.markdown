---
layout: post
title: Bug or Feature?
time: "10:38"
extended: ":EXTENDED:"
---

For years, as my fans may^Wshould know, i've been using the [fetchmail](http://fetchmail.berlios.de/) (POP3) + [procmail](http://www.procmail.org/) (filter) + [mutt](http://www.mutt.org/) (sucks less) + [msmtp](http://msmtp.sourceforge.net/) (eSMTP) tool chain for emailing.  And yes, i use gmail.  All is very convenient. For the SMTP part, gmail automatically stores any mail you sent in the 'Sent' folder. As for POP3,  it can archive any mail you fetched (you can safely specify 'delete' on the client side). All these are very user-friendly and sweet.

But recently i just found that you cant get (via pop3) mails sent by yourself. This is really annoying for mailing lists (yes, i want to see my mails in the lists).  And it turns out that [it's a feature, not a bug](http://mail.google.com/support/bin/answer.py?answer=76163). Gmail smartly thinks it's a duplicate (ie. same message-id) and ignores it. One workaround is to enable ['recent mode'](http://mail.google.com/support/bin/answer.py?hl=en-uk&answer=13291) but that's really awkward. Another option is to use IMAP.
Because gmail's POP3 worked so well for me, especially its 'archive' feature is good for backup, i really wouldnt need IMAP, if not for this 'smart' dup-checking problem of pop3.  So i just changed my fetchmailrc to use IMAP (very easy, just some s/pop/imap/, s/995/993/) to fetch my mails. I can actually get the mails sent by myself then but there's another new problem: gmail's IMAP mistakenly encoded From:/To: address.  [It's a bug, not a feature](http://dev.mutt.org/trac/ticket/2997). Not fetchmail's, not mutt's, it's just gmail's bug.

And the bug is triggered by fetching with [advanced parameters](http://osdir.com/ml/mail.imap.general/2007-12/msg00014.html) (ie. BODY.PEEK).  fetchmail detects server imap version on-the-fly and if server's advanced (ie.  IMAP4rev1), it will [issue BODY.PEEK](http://src.opensolaris.org/source/xref/sfw/usr/src/cmd/fetchmail/fetchmail-6.3.8/imap.c) (around line 1094). And i dunno of any exposed options/interfaces for users to change it. We may patch fetchmail or mutt to cope with this problem. But we should not, as it's not a bug of fetchmail's or mutt's _at all_, it's totally fault of gmail's buggy imap implementation.

The workaround is to use a 'simple' (not so advanced) imap fetcher to avoid gmail triggering this bug.  [getmail](http://pyropus.ca/software/getmail/) fits well.  It's simple. It 'works' well [with procmail](http://pyropus.ca/software/getmail/faq.html#faq-integrating-procmail). It can be used as a drop-in replacement of fetchmail. And the configuration is also [cleaner](http://pyropus.ca/software/getmail/configuration.html).

As an amusement, i think we can remove all the words written so far and just write one sentence:

> Dont bother, use gmail webly.
