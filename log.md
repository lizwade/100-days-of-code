# 100 Days Of Code - Log

### Day 1: Monday 11 November 2024

**Today's Progress**: Worked through the School of Code pre-work on Javascript functions and developer tools

**Thoughts:** Today I struggled to find the sweet spot between being in and out of my comfort zone. Most of the Javascript basics were simple enough for me, as I once knew Java quite well (I have forgotten much of it, and I know they are different anyway - but the syntax of Javascript is very familiar). But then the developer tools in Chrome were really scary, and that tutorial seemed full of Javascript stuff we haven't covered yet (eg using the consolde to debug listeners, when we haven't even been introduced to them) and I felt a bit cross (unfairly) with the Odin Project people for jumping around like that. Clearly it is up to me to work out how to make the materials work for me: skipping if I don't need them, supplementing when they confuse me - but mostly just getting on with stuff. I need to get over my tendency to be a Very Diligent Student and submit completely to the teacher. My coding today was not pushable stuff so instead I'm linking to the latest commit of the recipe website I've been building.

**Link to work:** [Recipe Website](https://github.com/lizwade/odin-recipes/commit/a3b29554c5d6176c52428f39294b589f25c53f48)

<br>

### Day 2: Tuesday 12 November 2024

**Today's Progress**: Brushed up a bit of Python on Codewars

**Thoughts**: This is probably procrastination, but working with Javascript reminded me how much I enjoy the problem-solving of coding, and how fun it used to be to solve katas on Codewars. Since the Javascript tutorials weren't feeling like fun today, I logged back into Codewars for the first time in years, and decided to try a 5kyu kata in Python (which I taught myself to a beginner-intermediate level in 2020 when I had plans to become a data scientist). The kata was to take a colour specified as RGB and return the 6 digit hex. I'd forgotten the necessary methods in python and had to look them up (how to convert an int to a different base, how to force leading zeroes in a numeric string) but I knew what steps to take to solve the problem, and in the process of implementing a solution I also re-discovered some useful concepts like list comprehension. I spent a while pondering the best / most elegant way to force the input values inside the range 0-255 (which took me on a pleasing detour back into my dusty Stack Exchange account) and I eventually plumped for the most obvious and slightly longer (but very easy-to-read) implementation over a "cleverer" but cloudier one-line option. I am justifying this diversion into Codewars/Python on the basis that (a) learning by doing is better than letting tutorials wash over you, and even if it's in Python, I am revising fundamental algorithms etc, which will surely be helpful for School of Code, right? (b) It will be good to do katas in javascript once I know enough to get started, and (c) Python is great for back-end development, which is my current tentative hypothesis about where I'd like to focus. Or maybe it <em>is</em> just procrastination!

**Link to work**: [RGB-->Hex kata](https://www.codewars.com/kata/reviews/54bd821b518b8d73630000a0/groups/67348075c23b0c510fe21ea6)

<br>

### Day 3: Wednesday 13 November 2024

**Today's Progress**: Learnt the basics of Javascript functions

**Thoughts** Today I headed back to my javascript tutorial refreshed, and I enjoyed it! I already have a decent understanding of functions, but now I know the basics of how they work in javascript. I particularly like arrow functions, an exciting new toy. I had to take quite a few detours while studying this material, just to teach myself some basic javascript stuff I had apparently missed / skipped, like the ? conditional operator, and some of the string methods. But it was very satisfying finding the right string method to write the functions requested. The instructions were to write them in the console, but I decided to do it on an html page I added to my liz_test git repo, which was a useful way to also revise my git command line chops (and make sure I had something to push to GitHub, as per this challenge).

**Link to work**: [Javascript functions sandbox](https://github.com/lizwade/liz_test/blob/main/javascript_functions_sandbox.html)

<br>

### Day 4: Thursday 14 November 2024

**Today's Progress**: Finished my first javascript kata and the first iteration of a timeIt function

**Thoughts** This was a simple 8kyu kata, but interestingly my solution differs from most on the codewars site: most people used if/else statements to test whether the value was >=5, whereas I used the Math.round() function (after a quick check of the documentation for javascript Math methods) to do the work for me. This seemed elegant to me, but possibly it's more computionally expensive? This made me miss the timeIt magic function that Jupyter notebooks offered for your Python code. A quick google revealed there is no equivalent in JS so I wondered if I could write one. Since functions are values in JS (!!) I can pass the function I want to test as an argument to the timeIt function, and (in theory) the argument(s) to be tested as a second argument to timeIt. I did manage to get this working for single parameter functions (enough for this kata - although I was too distracted to complete the comparisons) but I haven't yet solved the problem of how to make it work to test functions with any number of arguments. I thought about overloading the function with versions for 0,1,2,3 parameters, but turns out you can't overload functions in JS. I then discovered the ... spread and rest operator, which sounds like exactly what I need, but my code is buggy / I'm not unpacking the arguments properly or something. I'm not au fait enough with JS debugging yet to solve this, so that's what I'll work on tomorrow.     

**Link to work**: [Fake Binary kata](https://github.com/lizwade/javascript_katas/blob/d3f7db43265309a25dc1b01da310ab7824ed652a/javascript_katas.js)

<br>

### Day 5: Friday 15 November 2024

**Today's Progress**: Nailed recursion, and invented Euclid's algorithm (almost)

**Thoughts** I'm learning so much every day. Not necessarily what I'm supposed to be learning, but whatevs! My debugging plans were cast aside this morning, as I decided instead (inspired by yesterday's pre-work videos about problem-solving) to search the codewars katabank for a challenge in javascript tagged with 'recursion'. I wanted to kill two birds with one stone: practise javascript, and have another go at getting to grips with recursion, which I've always struggled to retain. The kata was to write a function to find the greatest common divisor of two integers. This sent me down a maths rabbit hole, which was lovely and reminded how much I like pure things. Through trial and error I worked out what I thought was a correct recursive algorithm that involved feeding the remainder from dividing the two integers back into the function with one of the integers. Coding it was easy once I let go of the fear of losing one of my original inputs. I made a note to self: in an iterative algorithm, we do DIFFERENT things to the SAME inputs. In a recursive algorithm, we do the SAME things to DIFFERENT inputs. Of course, the latter relies on proper mathematical equivalences - and this sent me down another rabbit hole, revising proofs by induction. I got a bit too tired to try proving my algorithm, so I rashly submitted it instead, and found that it passed nearly but not quite all the tests. I couldn't identify the error, so consulted the internet, where I discovered my algorithm was the same as an improved version of Euclid's (not bad!) but I was calling the recursive function with the two arguments in the wrong order. A quick switcheroo later and I had passed my second javascript kata.          

**Link to work**: [Greatest Common Divisor kata](https://github.com/lizwade/javascript_katas/blob/5d52c44a90f6b39b3c37214052802f1bd9748df8/greatest_common_divisor.js)

<br>

### Day 6: Monday 18 November 2024

**Today's Progress**: Got a lesson in humility thanks to javascript arrays

**Thoughts** I picked another recursive kata, this one featuring arrays, thinking it would be a good way to get to familiarise myself with them. I thought I knew what needed to be done, and leapt into the code. But I am doing soemthing wrong re the arrays, and am getting strange output. I spent about an hour just sort of guessing what to change, without hitting on the solution (not surprising since I did not know where or what the problem was). I would have preferred to step through the code and debug it properly, but I still haven't worked out how to do that. And since that is probably a longish project, I was trying to avoid it. But there's no way round it - I have to get to grips with the debugging process (presumably in Chrome, as per our learning materials). It's late now so this will be my mission for tomorrow. This time I won't let myself get side-tracked!    

**Link to work**: [Recursive Replication kata - not working](https://github.com/lizwade/javascript_katas/blob/4c719fa00f60a71188decf9d0d09634ab87ca31a/recursive_replication.js)

<br>

### Day 7: Tuesday 19 November 2024

**Today's Progress**: Practised debugging in Chrome (and thinking on paper)

**Thoughts** In Andy Harris' video lecture "Think Like a Programmer", he talks about the importance of working out the logic of something on paper before starting to code, and how he likes to slam his students' laptop lids shut if they reach for the computer too soon. As a lover of pencils, I took this to heart this morning, and wrote out all the contents I expected my stack to have through its layers of recursion. This clarified how the two arguments needed to change in each layer, and therefore what the recursive call needed to be. I also realized I could solve my dilemma of not being able to "hold on" to the number once I'd converted it to an array, by simply grabbing the 0th element of the array each time, which will always be the number, and pushing that on to it (instead of pushing arrays on to arrays, which openend a world of pain that the spread operator seemed unable to fix). I still had to add "debugger" to my javascript in quite a lot of places (today's new toy) but with this, and adding breakpoints by clicking, I was able to follow the steps in the Chrome dev tools, and fix my errors.   

**Link to work**: [Recursive Replication kata - working!](https://www.codewars.com/kata/reviews/575480c3a1445b44bc0000e7/groups/673c8b95feb88320e6332d3a)
