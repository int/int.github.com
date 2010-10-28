---
layout: post
title: logbot for LinuxFire/Linuxfans
time: "23:19"
extended: ":EXTENDED:"
---

<i><b>If it's too ugly, it's most likely not right.</b></i>

Wrote a simplistic log-only bot for LinuxFire, in perl, using <a href="http://search.cpan.org/dist/POE-Component-IRC/">POE::Component::IRC</a> (5 stars!!, far better than Net::IRC, imo).

Things become fairly easy when developing apps on top of <a href="http://poe.perl.org/">POE</a>. Totally event-driven (kinda like signal/sigaction).  Read some sample code, glanced at the POD of Poco::IRC, and then rolled out a raw bot (along with a cgi script to show the log on web).

Fine-tuning it cost more. (No bugs; just features to add ;P).  Now <a href="http://linuxfire.dhis.org/chatlog">the final results</a> come with aligned nicks and wrapped texts[1] (pretty much like what's shown within your xchat client =).

PS, ptlink's ircd has 'ForceServicesAlias' enabled in 'network.dconf' by default. That is, no '/msg /nickserv xxxx' (raw form: privmsg nickserv xxxx) allowed, only '/nickserv' (raw form: nickserv xxxx) works. Not convenient, really. Many servers offer the /msg style and many clients assume that. So i disabled 'ForceServicesAlias' for LinuxFire to not let "many" clients (our logbot included) down. :^)

[1] Using Text::Wrap

