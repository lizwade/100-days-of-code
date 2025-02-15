---
title: "AI: so clever, so stupid"
datePublished: Thu Feb 13 2025 00:00:00 GMT+0000 (Coordinated Universal Time)
cuid: cm764ras3000008jv5lma4rbi
slug: ai-so-clever-so-stupid
tags: ai, v0

---

Yesterday we were introduced to V0, an AI from Vercel that can build and deploy apps from your prompts. Chris at School of Code has used it to make a simple flashcards game. Once I’d got over feeling downhearted about my job prospects in this strange new world, it occurred to me that it would be a good tool to help me achieve the piano-keyboard drop down menu component I’d dreamt up as a login mechanism for my Mystery Musical Bootcampers. I had been envisaging weeks of painstakingly photographing keys from my piano, in various states of being pressed (with fingers photoshopped out), plus much gnashing of css teeth and grappling with animation libraries trying to put it all together into a working component. Instead it took V0 3 seconds (literally) to produce this:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1739617184566/0c6dfc73-9f5e-4597-b041-3c9b43936b0b.png align="center")

It’s touching isn’t it, in its almost-ness. Like when a child brings you a drawing featuring the sky as a blue line. I asked it to reverse the keyboard, thinking that would be an easy matter for it. It was not. Here is version 2:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1739617456740/e0ec480c-e5f0-4b73-9223-0fd124af8497.png align="center")

When I pointed out that it hadn’t reversed the piano, it was contrite. “You're right, I didn't properly reverse the piano. Let's correct that,” it said. And then it gave me this:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1739617577518/c940610a-93b5-4849-b9cf-609cdf12ec69.png align="center")

I felt a chill of actual horror at this, especially given the accompanying assertion “This layout now correctly represents a reversed piano with the black keys at the top and the white keys extending from the bottom.” Perhaps the word “reverse” had caused it to get mixed up with one of those jazzy pianos where the white keys are black and the black keys are white. But upside-down. Whatever the reason, I realised something big from this: once an LLM has taken a wrong step, kill it immediately. Start again, or revert to a previous version from which iteration can recommence. Like evolution, it can only increment from where it already is. It can’t take a clean look at the whole picture and assess what a good strategy might be. It can only stumble forwards, so once it’s dodgy ground, it’s highly unlikely to stumble anywhere fruitful. Luckily, unlike evolution, AI has an undo button. (For now, at least.)

In this case, I decided the best option was just to start again with a better prompt, which would prevent this mistake occurring in the first place. This time I was able, in five iterations, to get to this:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1739618447184/04595c8d-82fa-4e2a-9de0-adfb910da02a.png align="center")

As well as looking nice, it works beautifully. I copied the code and added it to my project as a React Component. Since it’s self-contained and I won’t need to understand or alter the code (except to pass in props and a callback function), and since my CSS skills aren’t something I’m too bothered about improving, I’m happy to just magpie it wholesale. It seems like a good use case for AI-generated code. (Unlike the way we tried to use V0 today - more of that later!)