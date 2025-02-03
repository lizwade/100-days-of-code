---
title: "Getting friendly with PostgreSQL"
datePublished: Mon Feb 03 2025 17:58:40 GMT+0000 (Coordinated Universal Time)
cuid: cm6pcu5ea000109jrddf6en9y
slug: getting-friendly-with-postgresql
tags: postgresql

---

I’m getting more pleasure than I perhaps should be from reading about the various data types one can store in a postgres database. Our previous exercises had used VARCHAR(255) which seems unnecessarily long to me for storing a name, but appears to be the (obsolete) standard because it was once the maximum size that could be accommodated. The current postgreSQL documentation is fond of VARCHAR(80) suggesting lower maximums are acceptable, so I’ll just use whatever value seems sensible in my fields. From what I can see, there are no performance gains from specifying shorter maximums. Apparently there can be performance gains from using fixed width types when the length is pre known and unchanging (such as CHAR(5) for US zip codes), but only if the whole table uses fixed width data types. If there are *any* columns of varying width then the benefits are lost.

I’m also trying to understand from the postgreSQL documentation (which I’d say could do with a bit less wry humour and a few more tangible examples) how to get an auto-incrementing integer primary key column, and also whether I can generate a UUID and use it as a one-time long in code. There doesn’t seem to be a type URL, so I guess I’ll have to use a VARCHAR with some regex.

\[Some time later…\]

After several failures due to missed commas, I seem to have successfully set up my database tables and seeded them! I can’t actually check, since I haven’t implemented any Read functionality in my app yet. That will have to wait until tomorrow.