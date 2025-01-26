---
title: "Learning by building"
datePublished: Sun Jan 26 2025 21:26:51 GMT+0000 (Coordinated Universal Time)
cuid: cm6e4r2ap000009labjwbayev
slug: learning-by-building
tags: forms, reactjs

---

I continued with my Mystery Musical Bootcampers app. Having read a bit about whether it’s better to start a full stack project - and in particular a React project - with the back end or the front end \[internet verdict: sometimes one, sometimes the other, or perhaps a “vertical slice” \] I quickly realised I would have to start with the front end anyway, since we haven’t learnt how to integrate React with an API yet. I don’t want to spend my whole Sunday trying to teach myself that when we will probably be covering it next week. So the UI it is! That still involves lots of data manipulation, albeit with dummy data hard-coded as state in App, rather than fetched from a database.

Resources I googled today:

[https://stackoverflow.com/questions/52621169/react-props-should-i-pass-the-object-or-its-properties-does-it-make-much-diffe](https://stackoverflow.com/questions/52621169/react-props-should-i-pass-the-object-or-its-properties-does-it-make-much-diffe)

[https://www.youtube.com/watch?v=zkFpxF1E4MM](https://www.youtube.com/watch?v=zkFpxF1E4MM)

[https://react.dev/reference/react-dom/components/input](https://react.dev/reference/react-dom/components/input)

[https://www.simplilearn.com/tutorials/reactjs-tutorial/how-to-create-functional-react-dropdown-menu](https://www.simplilearn.com/tutorials/reactjs-tutorial/how-to-create-functional-react-dropdown-menu)

[https://stackoverflow.com/questions/61937949/how-to-make-dynamic-radio-button-in-react](https://stackoverflow.com/questions/61937949/how-to-make-dynamic-radio-button-in-react)

[https://stackoverflow.com/questions/122102/what-is-the-most-efficient-way-to-deep-clone-an-object-in-javascript](https://stackoverflow.com/questions/122102/what-is-the-most-efficient-way-to-deep-clone-an-object-in-javascript)

I started from the top down, and I think this was a mistake. I got pretty tangled up over whether I was dealing with all the boot campers or one boot camper, what I needed to hold in state in various places, and whether it was secure or efficient to be passing the whole database as props to every component that needed to access a part of it. I found myself recalling the advice to “solve it for ONE example first”, and “solve a simpler problem” and so decided to temporarily abandon the app structure I‘d started to build, and to return once again to just getting the form to work for an imaginary, already-verified boot camper. I figured that would clarify what data the “leaf” or “youngest” component (probably not the correct technical terms) actually needs.

Today I got as far as this.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1737926576778/ebd786b8-63a2-434d-9ed3-a9a7d9165896.png align="center")

It’s neither pretty nor functional, but it is at least using props to display the dummy data in the fields, ready for editing. (I figured, since I need to specify the boot campers in advance, every submission can be a PUT rather than a POST request. If it’s the first time submitting then the database fields will be empty strings and thus the form will be empty. If they’ve submitted before and want edit, they will see their previous entries in the form. Next step is a bit of CSS to keep up morale, and then it will be time to bite the back end bullet.