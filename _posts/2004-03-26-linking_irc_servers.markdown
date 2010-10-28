---
layout: post
title: linking IRC servers
time: "21:10"
extended: ":EXTENDED:"
---

All starts from <a href=http://linuxfire.dhis.org/~fktpp/>FKtPp</a> asking me if i can help link <a href=irc://linuxfire.dhis.org>the irc server</a> of  <a href=http://linuxfire.dhis.org>LinuxFire</a> and <a href=irc://irc.linuxfans.org>the irc server</a> of <a href=http://www.linuxfans.org>LinuxFans</a>.

I once played with <a href=http://www.ptlink.net>ptlink</a> but got no experience linking 2 ircd servers. So..time to dig out more. =) Linuxfire was running <a href=http://www.unrealircd.com/>unreal</a> for its irc server, which uses a different config style from those traditional 'xLines'.  Well, xLines may look obscure at the first glance but once you get used to it, you just start to feel comfortable with it. Much simplier, actually.

So first step is to replace unreal with ptlink. One reason is for that xLines config style and another is because it might be easier to link two same ircd servers (ptlink to ptlink). FKtPp installed one from apt-get. We wasted a lot of time configuring it but it did not work. It could not even start listening on socket, always complaining 'address family not supported'. Dunno why. FKtPp said it might have something to do the IPv6 stuff. Not sure, though. So i just grabbed a source tarball from <a href=http://www.ptlink.net>ptlink's web site</a> and compiled it manually. Pretty easy to install and configure. It was going without any problems. 

And the next, yes, do the real linking. Linking 2 servers needs to configure both ircd servers. I wasnt able to access the irc server of linuxfans at the time of trying. So i installed a ptlink on my own box and started to try linking it with the server on LinuxFire. [Insert here 1,000 fail-and-trials and 1,000 struggles] [Insert here 3 hours and 10 cups of coffee].  Could link the 2 servers (ircd to ircd, with no services) but once services started, the connection got lost. And then figured out that i missed a H-line on the leaf's config file...
Everything seemed okay and the test went fine. <a href=http://www.gnome-cn.org>Penguin</a> showed up in irc.linuxfans.org and then i called up him to config the LinuxFans side (as hub). [Insert here some little pitfalls] and i did the LinuxFire side (as leaf) configuration. (actually, i also accessed irc.linuxfans.org and did that side's configuration then.)

Finally...the linking succeeded and worked fine. LinuxFire now connects to LinuxFans and both sides use LinuxFans' services.

Well, linking configuration summed up here: 

3 files should be cared enough:  ircd.conf network.dconf services.conf (the last file is for services; the side running no services does not need this one).

<ol><li> Make sure that ServicesName(or ServicesServer)s are the same in network.dconf and services.conf (carefully!!)</li>

<li> Add these C/N lines to the hub's ircd.conf:
C:ip_of_leaf:passwd:hostname_of_leaf::40
N:ip_of_leaf:passwd:hostname_of_leaf::40</li>

<li> Add these H/C/N lines to the leaf's ircd.conf:
H:*:host_name_of_hub
C:ip_of_hub:passwd:hostname_of_hub:port_of_hub:40
N:ip_of_hub:passwd:hostname_of_hub::40</li></ol>

(The difference here is that the leaf should have the H-line and have the port specified in the C-line.)


Well, look back on all of this stuff.. Much time has been wasted..indeed. The config file 'ircd.conf' is, in fact, pretty self-contained (read those comments!).

Configuring ircd servers is not as easy as setting up a mail/http/ftp server. (Oh..yes..blame those fscking xLines.)  Documents/guildlines are hard to find. Either not existing or out of date. Anyway, here are some links that hopefully could help in some way:

<ul><li><a href=http://www.irchelp.org>www.irchelp.org</a> Various docs, especially <a href=http://www.irchelp.org/irchelp/ircd/ircdinst.html>this one</a>.</li>
<li><a href=http://www.ptlink.net>www.ptlink.net</a> Ptlink's home.</li>
<li>#ptc @irc.ptlink.net  Technical channel for discussing ptlink's ircd & services.</li></ul>

PS, thanks FKtPp for trusting & providing me with the root access on the LinuxFire and Penguin for trusting & letting me access the irc.linuxfans.org to do the config.
