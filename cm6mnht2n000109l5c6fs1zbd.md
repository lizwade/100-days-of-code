---
title: "Full stack here we come"
datePublished: Sat Feb 01 2025 20:33:41 GMT+0000 (Coordinated Universal Time)
cuid: cm6mnht2n000109l5c6fs1zbd
slug: full-stack-here-we-come
tags: react, full-stack

---

I have found exactly the walkthrough video I need to stop faffing and get up and running.

<iframe width="560" height="315" src="https://www.youtube.com/embed/mKmxc8TcWQ8?si=r4TItyGguxXyTUMf"></iframe>

Thank you Arpan!

By following this tutorial (much of which was revising things I’d already done) I was able to get a server up and running, and move my hard-coded data server-side, and one step closer to being rehoused in a database.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1738419253965/73260e4a-a589-4186-98e9-146d74a58327.png align="center")

I had to google a few things from the video that were new to me.

1) **Nodemon**. This appears to be a utility that watches for changes to your code and restarts your server automatically to keep it up to date. But we’ve been achieving the same thing by using the script `“dev”: node —watch server”` in the package.json. [Turns out](https://vazgen6.medium.com/goodbye-nodemon-693a2c9b370c#:~:text=js%20projects%20in%20the%20past,and%20automatically%20restart%20your%20server.) the watch flag was new for node.js 18, and Nodemon is now unnecessary. This led me to my first `npm uninstall` command, which I found very satisfying. I do like a lean program.

2) **Axios**. [Research reveals](https://www.geeksforgeeks.org/difference-between-fetch-and-axios-js-for-making-http-requests/) that this is a js library that you can use to make http requests to node.js. It’s an alternative to using `fetch` and has some extra bells and whistles. I don’t need extra bells and whistles, so I’d prefer not to use it, but having got it working (and not being exactly sure how to use `fetch`) I will keep it in for now.

3) **CORS**. This one seems worth keeping - in fact I don’t think my app will work without it. It stands for [Cross Origin Resource Sharing](https://www.dhiwise.com/post/cors-in-react-essential-techniques-for-web-developers) and it’s middleware that lets your client at one address fetch data from a server at a different address, which would otherwise be blocked for security reasons.

4) **useEffect**. Not actually new to me, but controversial, as the React documentation is very clear that this hook should only be used as a last resort. I googled what the alternative was for fetching data, and discovered a lot of developers have very strong feelings about this. It seems that, since we need React to sync up with this external data, there is no way around using `useEffect` except for using a library (which is probably using it under the hood anyway). [The verdict](https://www.reddit.com/r/reactjs/comments/15yz949/how_to_actually_fetch_data_in_react/) seems to be “There's absolutely nothing wrong with having a useEffect run on mount (\[\]), that calls fetch and writes the data to state.” Apparently by using a simple js fetch instead of a library, I might eventually run into issues around edge cases with cancellation and race conditions, at which point I might want to turn to a third party solution like TanStack useQuery. But until that point, I liked this approach, suggested by [a reddit user](https://www.reddit.com/r/reactjs/comments/15yz949/comment/jxexuuf/?utm_source=share&utm_medium=web3x&utm_name=web3xcss&utm_term=1&utm_content=share_button):

> it's good to investigate the fundamentals. In that case, you might try the following progression:
> 
> 1. Fetch data with `useEffect` inside the components
>     
> 2. Grow your app in size and complexity. Refactor to write a separate function ("hook") that fetches the data, then call that function in the components
>     
> 3. Grow some more. Add features to your fetching function, such as caching, pagination, lazy loading, deduplication
>     
> 4. Grow some more. Extract your (now complex) hook into a separate library locally. It's getting complex so add some unit tests
>     
> 5. Realize that you reinvented one of the popular libraries :)
>     
> 
> You'll learn a lot this way, and knowing the internals and use cases of fetching libraries will also help you intuitively use them.

Getting the front end to fetch the data from the back end, and setting it as state in App using useEffect, was surprisingly smooth. But it took me a loooooong time to work out how to then pass that state down as props to the child components that needed it. The problem was good old async again. The child components were being rendered before the data fetch had completed, which meant the state passed to them as props was the initial undefined state and not the data. Eventually I worked out I needed to render something static while waiting for the promise to be fulfilled. It was as simple as

```javascript
  if (bootcampers === null) {
    console.log("no data in bootcampers yet...");
    return <h2>loading!</h2>;
  }
```

Once I’d solved that problem, and seen all my lovely back-end data appear in my (still very ugly) form, I had some fire in my belly again. I did a git commit before I even breathed, just in case something broke it, and while I was at it I set up Github milestones and issues to act as a Todo list for the tasks to come. A good day’s work, I’d say.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1738441357511/0ddf3cc2-13b3-457e-8de5-fe1ae05f8feb.png align="center")