---
title: "The brain is an auto-refactor machine"
datePublished: Sun Jan 19 2025 10:32:57 GMT+0000 (Coordinated Universal Time)
cuid: cm63hb6iv000108js21iu0ues
slug: the-brain-is-an-auto-refactor-machine
tags: refactoring, tdd

---

Most of the work I’m proud of has been delivered to me, unbidden, by my waking brain. Back when I was making music, I would often wake up with an almost complete song in my head. Of course, I then had to spend several effortful days implementing it, but the hardest part was done without my conscious knowledge. At School of Code I don’t have the luxury of following the erratic pace of my unconscious, and there’s not much mental down time for thoughts to quietly bubble-sort themselves up into awareness. So it was nice when this morning I woke up with a simpler solution to Fergus’ kata, fully-formed and ready for my fingers to type.

Fergus’ challenge was to write a function which returned an updated value for enemy health when passed the name of a gun, with different guns doing different specified amounts of damage. Here’s what I wrote at the time:

```javascript
export function enemyHealthCalculator(gun) {
  let enemy_health = 100;
  const guns = [
    { name: "Pistol", damage: 20 },
    { name: "SMG", damage: 5 },
    { name: "RPG", damage: 100 },
  ];
  const gunWeWant = guns.filter((entry) => entry.name === gun);
  console.log(gunWeWant);
  return enemy_health - gunWeWant[0].damage;
}
```

It passed the tests, but it felt overly-complex. I knew there was a simpler way, but couldn’t work it out it in the pressure of the moment (especially given that, because of a mix-up with kata swapping, I was live-coding this while screen sharing and Thinking Out Loud in front of seven other boot campers).

Then this morning, after the respite of a Saturday, this unexpectedly popped out and demanded to be typed before I’d even had a cup of tea:

```javascript
//better, simpler version!
export function enemyHealthCalculator(gun, enemy_health = 100) {
  const gunDamageDictionary = {
    Pistol: 20,
    SMG: 5,
    RPG: 100,
  };
  return enemy_health - gunDamageDictionary[gun];
}
```

Apart from the decision to change `enemy_health` to a parameter (because it wasn’t smart to be declaring and assigning it in a function that’s meant to update it), the change is from having each gun be an object, to having a single object - a dictionary of gun damage values - which allows us to look up the damage. There are cases where the first implementation would be more suitable: perhaps if we knew we were going to need to store additional information about each gun, such as its ammo capacity or its weight. Or if we knew there were cases when we would need to get hold of several guns at once rather than just one (the use of the `filter` function would make that an easy amendment). But In terms of writing a clean kata and adhering to the TDD principle of writing the simplest code that will pass the test, I think the second implementation does a better job.

I really like how TDD clarifies these decisions. I feel like it provides a brief which lets you mentally separate the basic requirement (to write a function that does the job) from the nice-to-have considerations (what might you want it to do in future? what algorithm might perform better?) Sometimes there might be good reasons to take account of these nice-to-haves, but mostly: YAGNI. As someone who struggles with perfectionism, this separation helps me to avoid “boiling the ocean”, which the ever-pithy Nadeem said this week is the hardest thing to teach junior developers.