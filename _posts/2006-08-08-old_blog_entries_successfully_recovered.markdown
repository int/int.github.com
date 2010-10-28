---
layout: post
title: Old Blog Entries Successfully Recovered
time: "20:18"
extended: ":EXTENDED:"
---

Great thanks to [hf_linux](http://linuxfire.com.cn/~hf/), all old data of ~ on 40 has been recovered.

As for my old MT blogs, just export them from the old MT and then import them to the new MT.  Works like a charm. 

 I have disabled comments and trackbacks of the old blogs. Now with the (hopefully good) antispam plugins along with MT3.31, i want to re-enable those feedback functions of old entries. A simple sed will do:

`$ sed -e 's/ALLOW PINGS: 0/ALLOW PINGS: 1/' \  
-e 's/ALLOW COMMENTS: 0/ALLOW COMMENTS: 1/' old.txt >new.txt`

And then import the new one without any errors.

And for the nanoblogs, luckily they have the similar format to MT.  So here's a small perl  script to do the transfer:

	#!/usr/bin/perl -wp
	
	use strict;
	
	my @month = ("", "Jan", "Feb", "Mar", "Apr", "May", "Jun",
		"Jul", "Aug", "Sep", "Oct", "Nov", "Dec");
	
	if (m/^DATE: /) {
		my @time = split(' ');
		my $i = 1;
		while ($month[$i] ne $time[2]) {
			$i++;
		}
		$_ = "DATE: $i/$time[3]/$time[6] $time[4]\n";
	} elsif (m/^END-----/) {
		$_ = "\n\n--------\n";
	}

Plain text always rox.  MT rox, also, indeed.

