---
title: "Focus"
datePublished: Mon Feb 03 2025 15:26:57 GMT+0000 (Coordinated Universal Time)
cuid: cm6p7f1jx000909kv9xhb5pef
slug: focus
tags: bugs-and-errors, html-input-elements

---

I am one bug away from MVP1.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1738575787188/f1cc17a6-c185-45e2-a224-12ffb2cfef86.png align="center")

I started googling this problem, which led me to try tabbing into the fields with the keyboard. This revealed the text *is* actually editable, and the problem is to do with gaining focus from the mouse. So I think it’s the CSS that’s causing the bug, not the jsx. Re-sizing the window revealed that when the input box for band name wrapped on to the next line, it became able to gain focus with the mouse. I think maybe I have some overlapping elements which are preventing a click on the right thing. However I don’t feel inclined to spend more time on this right now, as the next round of styling might make it moot. I’m going to leave the ticket open and declare MVP1 complete, so I can get on to the delights of setting up a database!