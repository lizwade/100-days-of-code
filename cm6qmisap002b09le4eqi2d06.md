---
title: "Rethinking React"
datePublished: Tue Feb 04 2025 15:17:32 GMT+0000 (Coordinated Universal Time)
cuid: cm6qmisap002b09le4eqi2d06
slug: rethinking-react
tags: reactjs

---

Last night was Monday, which meant choir rehearsal, which meant a couple of hours of enforced absence from my laptop. But not from thinking about the problem! In fact, having to think with my brain and a pencil instead of the computer gave me some much needed space to think about my design a bit more. I jotted down the following on the back of Grieg’s “Ein Traum”.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1738664854157/f3d8a10a-72cd-4176-bd72-0ab4f132dfff.png align="center")

What it made me realise is… it really doesn’t make a lot of sense to be using React for my front end. Not THIS front end anyway. My project has *two* front ends - this part, which is collecting data from a user and storing it in a database, and the other part which is a game. For the other part, React makes a lot of sense. There will be various user interactions, and we want them to update the UI as the user plays. But here, a user is only typing info and submitting a form. There’s nothing for React to ever re-render, and having to route the data around the React components as props and state just adds complexity. A simple html form could call a function to write its contents directly to the database, without needing to use callback functions passed down from App so App can update its state and then write that to the database. But then again, App will still need to exist and to hold the database’s contents in state in order for the game to be played. So is it really a problem? I feel like it would take me longer at this point to ditch the React and start again than to just continue. Or is that me being too attached to my code? I think I will write some CRUD functions now, and give the question some time to percolate.