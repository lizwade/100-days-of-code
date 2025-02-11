---
title: "Typescript at last!"
datePublished: Tue Feb 11 2025 18:26:21 GMT+0000 (Coordinated Universal Time)
cuid: cm70tckew000009jgc51ggdnf
slug: typescript-at-last
tags: typescript, enum

---

I remember telling my mentor, Steve, in my first fortnight of School of Code, that I was pretty freaked out by the Wild West world of Javascript, where variables could transition from strings to booleans to objects and back again willy-nilly, where numbers weren’t ints or floats or doubles (but might be any of them) and where functions with three parameters didn’t care if you passed them one argument or twenty. How is anyone supposed to know what’s going on?? He reassured me I would feel a bit better when we got to Typescript, and told me all about enums to calm me down.

Today we did indeed get to Typescript. And it was fun to force all those ambiguities out of hiding, and slay them with proper function signatures and lovely interfaces (although those numbers are still as elusively generic as ever).

We were given a rock paper scissors game to convert to TypeScript. Here’s some of the provided code:

```javascript
/** Some related "constants" which represent the various outcomes a round can have. */
export const OUTCOME_WIN = "WIN";
export const OUTCOME_DRAW = "DRAW";
export const OUTCOME_LOSS = "LOSS";

/** Some related "constants" which represent the possible choices a player can make when playing. */
export const CHOICE_ROCK = "ROCK";
export const CHOICE_PAPER = "PAPER";
export const CHOICE_SCISSORS = "SCISSORS";

/** Should return a randomly selected choice. Either: "ROCK", "PAPER", "SCISSORS" */
export function getRandomComputerMove() {
  const choice = Math.trunc(Math.random() * 3);
  switch (choice) {
    case 0:
      return CHOICE_ROCK;
    case 1:
      return CHOICE_PAPER;
    case 2:
      return CHOICE_SCISSORS;
    default:
      throw new Error(`Unsupported choice: ${choice}`);
  }
}

/** Should return either: "ROCK", "PAPER", "SCISSORS" (or null if the user cancelled)*/
export function getPlayerMove() {

//more code 
```

I got MVP1 working by creating a couple of interfaces so I could enforce a shape for some of the data used further down the program, and adding some type declarations to function parameters and returns.

```typescript
/** Some related "constants" which represent the various outcomes a round can have. */
export const OUTCOME_WIN = "WIN";
export const OUTCOME_DRAW = "DRAW";
export const OUTCOME_LOSS = "LOSS";

/** Some related "constants" which represent the possible choices a player can make when playing. */
export const CHOICE_ROCK = "ROCK";
export const CHOICE_PAPER = "PAPER";
export const CHOICE_SCISSORS = "SCISSORS";

interface DataForRound {
  playerMove: string;
  computerMove: string;
  outcome: string;
}

interface Model {
  playerScore: number;
  computerScore: number;
}

/** Should return a randomly selected choice. Either: "ROCK", "PAPER", "SCISSORS" */
export function getRandomComputerMove() :string {
  const choice = Math.trunc(Math.random() * 3);
  switch (choice) {
    case 0:
      return CHOICE_ROCK;
    case 1:
      return CHOICE_PAPER;
    case 2:
      return CHOICE_SCISSORS;
    default:
      throw new Error(`Unsupported choice: ${choice}`);
  }
}

/** Should return either: "ROCK", "PAPER", "SCISSORS" (or null if the user cancelled)*/
export function getPlayerMove() : string | null {
   
//more code     
```

That was all the task required, but I thought my mentor might be pleased to know I’d remembered the enums, so I consulted the Typescript Handbook and wrote an MVP2 turning those constants into string enums. String enums aren’t as flexible as numeric enums (you can’t increment them, for instance) but they still make things neater.

```typescript
export const enum Outcome {  
  Win = "WIN",
  Draw = "DRAW",
  Loss= "LOSS",
}

export const enum Choice {
  Rock = "ROCK",
  Paper = "PAPER",
  Scissors = "SCISSORS",
}

interface DataForRound {
  playerMove: Choice;
  computerMove: Choice;
  outcome: Outcome;
}

interface Model {
  playerScore: number;
  computerScore: number;
}

/** Should return a randomly selected choice. Either: "ROCK", "PAPER", "SCISSORS" */
export function getRandomComputerMove() : Choice {
  const choice = Math.trunc(Math.random() * 3);
  switch (choice) {
    case 0:
      return Choice.Rock;
    case 1:
      return Choice.Paper;
    case 2:
      return Choice.Scissors;
    default:
      throw new Error(`Unsupported choice: ${choice}`);
  }
}

export function getPlayerMove() : Choice | null {

//more code
```

Much more soothing, right? And maybe it’s just me, but seeing the shape of the parts right there at the top of the code makes the rest of the program feel so much easier to implement. The game logic flows from the clear structures. The functions practically write themselves.

[Not everyone likes Typescript’s enums](https://www.reddit.com/r/typescript/comments/103nino/whats_up_with_all_the_enum_hate_lately/), it seems, so possibly this a questionable design decision. I’ll have to see what my mentor thinks!