# 100 Days Of Code - Log

### Day 1: Monday 11 November 2024

**Today's Progress**: Worked through the School of Code pre-work on Javascript functions and developer tools

**Thoughts:** Today I struggled to find the sweet spot between being in and out of my comfort zone. Most of the Javascript basics were simple enough for me, as I once knew Java quite well (I have forgotten much of it, and I know they are different anyway - but the syntax of Javascript is very familiar). But then the developer tools in Chrome were really scary, and that tutorial seemed full of Javascript stuff we haven't covered yet (eg using the console to debug listeners, when we haven't even been introduced to them) and I felt a bit cross (unfairly) with the Odin Project people for jumping around like that. Clearly it is up to me to work out how to make the materials work for me: skipping if I don't need them, supplementing when they confuse me - but mostly just getting on with stuff. I need to get over my tendency to be a Very Diligent Student. My coding today was not pushable stuff so instead I'm linking to the latest commit of the recipe website I've been building.

**Link to work:** [Recipe Website](https://github.com/lizwade/odin-recipes/commit/a3b29554c5d6176c52428f39294b589f25c53f48)

<br>

### Day 2: Tuesday 12 November 2024

**Today's Progress**: Brushed up a bit of Python on Codewars

**Thoughts**: This is probably procrastination, but working with Javascript reminded me how much I enjoy the problem-solving of coding, and how fun it used to be to solve katas on Codewars. Since the Javascript tutorials weren't feeling like fun today, I logged back into Codewars for the first time in years, and decided to try a 5kyu kata in Python (which I taught myself to a beginner-intermediate level in 2020 when I had plans to become a data scientist). The kata was to take a colour specified as RGB and return the 6 digit hex. I'd forgotten the necessary methods in python and had to look them up (how to convert an int to a different base, how to force leading zeroes in a numeric string) but I knew what steps to take to solve the problem, and in the process of implementing a solution I also re-discovered some useful concepts like list comprehension. I spent a while considering the many ways to force the input values inside the range 0-255 (which took me on a pleasing detour back into my dusty Stack Exchange account, as well as some incomprehensible regex). I plumped for the most obvious and slightly longer (but very easy-to-read) implementation over a "clever" but cloudy option. I am justifying this diversion into Codewars/Python on the basis that (a) learning by doing is better than letting tutorials wash over you, and even if it's in Python, I am revising fundamental algorithms etc, which will surely be helpful for School of Code, right? (b) It will be good to do katas in javascript once I know enough to get started, and (c) Python is great for back-end development, which is my current tentative hypothesis about where I'd like to focus. Or maybe it <em>is</em> just procrastination!

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

<br>

### Day 8: Wednesday 20 November 2024

**Today's Progress**: Algorithm revision and more array practice

**Thoughts** I didn't have much coding time today as I am busy sorting out my life admin before School of Code kicks off on Monday. I didn't finish filing my taxes until nearly 11pm, so after that it was just a quick kata so I wouldn't miss a day. I chose a bubble sort challenge, as it's good to revise these algorithms and also to practise working with arrays in javascript. Although actually it turns out you can directly assign a new value using indexing (I thought I'd have to use some special method). On my first attempt, I only included one loop to do one pass. I corrected that by adding an outer loop. My code does seem to sort the list correctly, but it is not currently taking all the right snapshots in all the right places as per the required output of the function. I'll have to debug it tomorrow!

**Link to work**: [Bubble sort kata - not working](https://github.com/lizwade/javascript_katas/blob/18cfffe46487a45c1cb27db70f7d77f0b8652b9c/bubble_sort.js)

<br>

### Day 9: Thursday 21 November 2024

**Today's Progress**: The joy of console.log

**Thoughts** It only took me a few minutes yesterday to write a close-to-correct bubble sort implemetation. It took me hours and much head-scratching to get from that broken thing to a fully functional version. My first problem, which took a lot of console.log commands to identify, was that the array of snapshots, which was supposed to keep a record of each state of the list, was losing its previous 'photos' whenever I pushed a revised list on to it, and I was ending up with dozens of copies of the final list instead. It took quite a bit of detective work to understand that in javascript, the push method only appends a *reference*, so if you change the state of the object it has a reference to, you change what appears in the array. This was unexpected behaviour (to me!), and it took me a while to discover the structuredClone solution to pass by value. (Later, when I failed the test because the buffer was full, I worried I was doing something with high space complexity, but it was just my zillion console.log messages flooding the system! I commented them out.) I also had to fix a logical error I'd make, thinking my outer loop could start from an incremented position each time instead of from the first element. Lastly, I had trouble meeting the requirements for if the argument is an empty array, because I was trying to discover this by testing its truthiness, but it turn out empty arrays are truthy or maybe falsy. That seemed weird and I couldn't quite get my head round it, but could easily take the advice to simply test the length instead. It was a good feeling to see the test page finally turn green!

**Link to work**: [Bubble sort kata - working!](https://github.com/lizwade/javascript_katas/blob/2afcf186b01bfa68bc24253947b5344c9bb63128/bubble_sort.js)

<br>

### Day 10: Friday 22 November 2024

**Today's Progress**: Got DOMmy with javascript

**Thoughts** I have been enjoying implementing elgorithms in javascript, but if that was what I was here for, I probably wouldn't be using javascript. My course starts on Monday and I have a feeling that making web pages interactive will be a more pressing use case. Currently when I look at most .js pages I see a bunch of webby stuff about Documents and Event this and that which I don't understand. So today I studied a chapter in my Head First JavaScript programming book to learn about how to manipulate the DOM with a javascript function that uses getElementById, the innerHTML attribute, and the window.onload command. It wasn't too tricky, and I'm quite excited to get more webby now.  

**Link to work**: [Using javascript to change the DOM][https://github.com/lizwade/experiments/blob/8a869a9ec3ef2d43dba60c1b7f4442197c9ac9bc/planets.html]

<br>

### Day 11: Monday 26 November 2024

**Today's Progress**: Letting go of perfectionism

**Thoughts** Today I started at the School of Code. Straight away, I was blown away by it. It's so much more than I was expecting, and about so much more than just code. I learnt a huge amount about meta-learning (the human kind), growth mindset, and ways to position ourselves professionally as Seniors Without Experience. What we didn't learn, yet, was anything involving code. Which is no problem - except for the need to complete this blog. I had assumed that this blog would kind of write itself once the course started, as I could just post something I'd done during my day. Probably that will be true later, but in the meantime, I don't think it's productive for me to try to do an hour of coding on top of what is already an intense day's work. As was emphasised today, we need to prioritise sleep. And we mustn't let the perfect be the enemy of the good. So I'm calling it that posting today with no code is better than giving up posting. (Confession: I'm actually posting this on Tuesday, when letting go of perfectionism was a topic. I've always struggled with this, so I'm taking it to heart!). 

**Link to work**: None today

<br>

### Day 11: Tuesday 27 November 2024 (honest)

**Today's Progress**: Releasing my inner Matthew Broderick

**Thoughts** As a tweenage girl in the 1980s, I wanted to be a boy. Specifically I wanted to be one of the boys in American films who types things in green writing into a black computer screen, which unlocks a maze of crazy graphics and alerts, because they've hacked into some mission-critical mainframe (Girls in movies did not get to do this). At SoC today, among many other things, we played a game where we had to try and trick an AI into revealing the password it was supposed to protect. It was a lot of fun trying to work out its vulnerabilities, and I made it to the end of 7 levels of hacking. It made me wonder if some sort of prompt-based cybersecurity could be an interesting career avenue. 

**Link to work**: [Gandalf game (I didn't write it; I just played it)](https://gandalf.lakera.ai/baseline)

<br>
<h2>SOME TIME LATER...</h2>
<br>

### Day 12: Tuesday 3 December 2024

**Today's Progress**: Objects, arrays, interpolated strings

**Thoughts** Okay so I missed a week. I've been too busy learning about problem-solving to actually code anything. Sorry. Now we are actually getting into JavaScript at School of Code, I am back! Today we worked on objects and arrays. I was amazed to discover you can pass a JS function fewer or more arguments that it's expecting and it will still work, just ignoring the extras or leaving the surplus arguments null (or undefined?). I didn't make use of this yet, but perhaps I can revisit my timeIt function with this knowledge. In the meantime, I applied my new toy of backtick strings with ${variables} interpolated right in them to build this makeABagel() function, using objects. 

**Link to work**: [My makeABagel() function (starting line 86)](https://github.com/SchoolOfCode/week-2-objects-recap-lizwade/blob/main/main.js)

<br>

### Day 13: Wednesday 4 December 2024

**Today's Progress**: Debugging: naked eyes are not enough!

**Thoughts** Today we worked on debugging. I like to think I have a decent eye for spotting bugs, but by the end of today I had realised that just scanning code and hoping errors jump out at you is not a smart or systematic way to do it. Much better to use everything the console has to tell you, and hunt the bugs down line by line. Our team turned a very buggy random number guessing game into something that worked nicely. Best of all, I discovered that if something has been tagged as a bug on GitHub issues, then if you do a git commit with a message of "fixes #7", say, then the bug with that number will auto-resolve! SO satisfying.

**Link to work**: [Random number guessing game, after our bug fixes (check the initial commit to see the mess we were handed!)](https://github.com/SchoolOfCode/week-2-debugging-customer-challenge-room12-wk2/blob/main/script.js) 

<br>

### Day 14: Thursday 5 December 2024

**Today's Progress**: A clearer idea of my strengths and preferences

**Thoughts** We started our hackathon this afternoon, but I'll save that code for tomorrow. This morning we took a Myers-Briggs test. (As always, even when I think "I'll try to answer the questions a bit differently this time", I came out INFJ). Afterwards we studied some scenarios where people with different preferences have to work together and decide what to do as a team. What struck me is that while the ad world I've come from is by nature quite "front end", and makes people assume I will gravitate to front end development, my *role* in that world was quite "back end". I was the strategist, making sure that what we created was the *right* thing, for the consumer and for the client's business (while it was the responsibility of others to make sure it was a beautiful thing, an affordable thing etc). This might explain the pull of back end for me. But it's still early days! 

**Link to work**: No code today.

<br>

### Day 15: Friday 6 December 2024

**Today's Progress**: A lesson in YAGNI

**Thoughts** We finished our second hackathon today. It was a Rock Paper Scissors game, and our team managed to complete all the tasks and several of the extension tasks, so that was pleasing. Even more pleasing was that we did it in what we thought was a smart, resusable, extendable way, with an array in which each element beats the one before it, using modulo arithmetic to wrap back round to the start. This abstraction made it very flexible, and we were able to complete the extension task (Rock Paper Scissors Lizard Spock) just by adding the two new items to the array and adding one additional test for the new losing rule. Our feedback, though, was that hard-coding the rules (given how simple they are) would have been quicker to do and easier to read, and I was introduced to the concept of YAGNI or "You ain't gonna need it". This chafes a bit with my original schooling in programming, which stressed thinking ahead and always aiming to write reusable code. But then again, that was a long time ago, before agile and XP were widely adopted. I guess (as my mentor said in our first meeting today) it's always a balancing act.   

**Link to work**: [Our Rock Paper Scissors game](https://github.com/SchoolOfCode/week-2-hackathon-rock-paper-scissors-room12-wk2/commit/5357b1fcd44e1148284b836f6bf6a7ee335aff75)

<br>

### Day 16: Sunday 8 December 2024

**Today's Progress**: Event Listeners (sort of)

**Thoughts** When I started this #100daysofcode log, I decided I would omit weekends. One needs a life, after all. But since I have allowed myself the flexibility to sometimes skip a weekday or two, I thought why not also be flexible in the other direction. So here is my first weekend entry, mainly because I am stuck and I feel the urge to document my struggle - not least because I'm sure I will look back on it with amusement once I know the answer. Tomorrow we will start our "front end" week, and our weekend prep project is a shopping list that uses event listeners on a button to add items to a list. I think I've got the gist of capturing the html elements as javascript variables so we can manipulate them. My problem has been lack of familiarity with the html elements themselves - eg I didn't know there is an element called <input> and its text lives in a field called 'value' - so I had to google a lot of things to work out precisely *what* to manipulate with the js. Now I've got it working nicely to add the items, but I can't get the delete button to delete the list item. The issue is, we want so set an event listener on the delete button which when clicked will delete the button itself, but also its parent node (I think), and I don't know how to specify that. From googling, the word <em>this</em> might be relevant, or something to do with e.target.parent. But most of my efforts either do nothing or (bizarrely) delete the *other* button on the page, which I don't understand at all!  
***UPDATE*** I spent two hours trying to unstick myself, and decided that was long enough, so I peeked at the answer, which I still don't understand. But I'm sure I will eventually! 

**Link to work**: [Shopping list](https://github.com/lizwade/sandbox/blob/main/shopping_list.html)

<br>

### Day 17: Monday 9 December 2024

**Today's Progress**: Doing cool things to web pages

**Thoughts** Today was a bit of a slow burn. We went down a DOM hole, confused by the difference between .children and .firstChild / .lastChild (the former selects only html elements, while the latter select any node including text - which is an illogical discrepancy if you ask me). This meant we didn't have enough team time to get very far through our exercises. But I decided to carry on solo this evening and I found it got easier as I went on and the process of grabbing and appending became more fluent. I particularly enjoyed using js to manipulate a big old dataset, and managed to write the code to grab everyone's names, ages and photos from the database, and turn it into a mini-facebook webpage - and with only a couple of little bugs that I was able to iron out straight away. So satisfying!   


**Link to work**: [Fledgling Facebook clone](https://github.com/lizwade/sandbox/blob/main/SOCbook/SOCbook.js)

<br>

### Day 18: Tuesday 10th December 2024

**Today's Progress**: DOM wizardy

**Thoughts** x

**Link to work**: [Star Slider] (https://github.com/lizwade/sandbox/tree/main/star_slider)


<br>

### Day 19: Wednesday 11th December 2024

**Today's Progress**: A very fetching web page!

**Thoughts** Husband's birthday tomorrow

**Link to work**: [Dog GIF generator] ([https://github.com/lizwade/sandbox/tree/main/star_slider](https://liquify.net/malc/)

<br>

### Day 20: Thursday 12th December 2024

**Today's Progress**: xx

**Thoughts** x

**Link to work**: 

<br>

### Day 21: Friday 13th December 2024

**Today's Progress**: Games with Fetch!

**Thoughts** Today was our hackathon (this week a "fetch-a-thon"). The team  


**Link to work**: team repository

