---
layout: post
title: Use ssh like a proxy
time: "16:19"
extended: ":EXTENDED:"
---

I used to use ssh tunnel for some connections. But tunnel has one limition: it's just a one-to-one map for the connections.  FKtPp today shared with me a kool tip to let ssh run like a socks proxy: ssh -D xxx xxx (see ssh man page for -D detail).  Never knew that before. It's very convenient for some occasions. Thanks pp. =)

