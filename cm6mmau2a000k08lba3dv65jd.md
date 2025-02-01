---
title: "Form decisions"
datePublished: Sat Feb 01 2025 20:00:17 GMT+0000 (Coordinated Universal Time)
cuid: cm6mmau2a000k08lba3dv65jd
slug: form-decisions
tags: forms, react

---

I don’t have confident answers, but at least I now have some questions!

---

## **Q1: React or just plain old javascript + html?**

It seems that most of what I want to do in my form can be handled with the built-in html elements and normal javascript. So is it overkill to make a custom Form component in React? It sounds like using React is still a good idea, since (a) it makes available React’s form handling capabilities and (b) the children of the Form component can still be plain html elements. So I’m saying:

### A: React.

---

## **Q2: Controlled or uncontrolled?**

Since I’m going to use React, I have the option to hold all the Form data as state (which, if I understand correctly, is what makes it a controlled component). This means the whole form would be re-rendered every time the user types, which has the benefit of allowing as-you-type validation, but the disadvantage of creating an unwieldy state object and a lot of re-renders. I don’t think i need to do this. The data doesn’t need to be in state - it only needs to be handled once the user has finished typing and presses the submit button, at which point it should be validated and sent to the server. Once it’s been written to the database, one re-render of the Form will keep the UI up-to-date with reality, because I’ve coded the Form to pre-populate its fields with the fetched current data. If I do need as-you-type validation for a particular field, it looks like I can make a controlled React component specially for that field and include it within the Form component, mixed in with the uncontrolled elements/components. The MixedForm example [here](https://dev.to/ajones_codes/a-better-guide-to-forms-in-react-47f0) seems like a good model.

### A: An uncontrolled Form component, or possibly a mixed component that holds state only for one or two controlled children.

---

## Q3: onSubmit or form action?

[This post](https://www.epicreact.dev/react-forms) claims that `action` is the better, modern way to send form data, rather than `onSubmit`. But it seems to be a new feature in React 19, and we’re using React 18 and there was some reason mentioned at the time for not installing the latest version, which I can’t now remember. So this may be moot.

### A: I don’t know yet but this is all a bit too abstract at the moment. I need to make some progress on getting a front and back end up and running and playing nicely, so I can work out what problems relate to form handling vs simply not having a backend yet…