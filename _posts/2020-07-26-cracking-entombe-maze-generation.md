---
layout: post
title:  "An Attempt to Crack the Entombed Maze Generation Algorithm"
date:   2020-07-25 21:12:04 +0530
categories: code study puzzle
---

_Work in Progress_

So I came across this problem in the List of unsolved problems in computer science - Wikipedia[^1] on a boring Saturday evening when I was randomly browsing the web.

## A bit of background

Entombed is an  Atari 2600[^2] game released in 1982.  The game has a very simple gameplay.  Try out the game here: [Entombed](https://www.retrogames.cz/play_1044-Atari2600.php?language=EN)

There’s a vertically scrolling maze (which is also symmetric) and player has to go through the maze avoiding enemies and picking up make-break boosters (which are useful for making a wall or breaking one)

The game has been subject to academic research particularly for its maze generation. Since the Atari 2600 had a limited ROM size, the mazes were too big to store on the ROM, and after researchers evaluated[^4] the game’s ROM, they found that the mazes were generated during runtime.



## The problem

The mazes that were produced in the game were unsolvable without efficient use of the make-break item (Which adds the game factor to it). However, during an interview with the Paul Allen Newell who previously worked on the game, it is said that they were able to come up with an algorithm which consistently generates solvable mazes in the interview with Paul Allen Newell[^3]

> The story of the algorithm is that one night after work, Duncan and I went out for a beer and ended up coming up with this “problem” of wondering whether one could generate an endless maze that always had a solution.  At the time, we weren’t thinking of a game per se, it just seemed like an interesting puzzle for us to solve.  We worked out the algorithm and, since I knew how to program a VCS system (Duncan was Vectrex only), I spent a weekend coding something up.  We were surprised at the elegance of the algorithm as it gave us the ability to dial in a “difficulty factor” (via a bit setting) and we could prove that there was not only a point where it became unsolvable

_(Here, “VCS system” refers to Atari Video Computer System)_

So the question I was actually interested in is

### Is it possible to come up with a maze generation algorithm which only produces a solvable maze using the 5 context bits (two bits to the left and three bits above)?


Simply upon inspection, we can see that the maze that is generated within the game itself is unsolvable. Although the title of this post is about Entombe and it's mazes, we're past that and I am starting to question why this problem is on the list of unsolvable problems[^1]. The maze generated isn't solvable and not special except for the aesthetics and a reddit thread about this in /r/programming seems to agree with me[^6], which sadly I stumbled upon only after spending enought time on this.

However, I will move on to defining a new problem and possibly try to answer it. 


## Solvability

A vertically scrolling maze of MxN grid (M width and N height) can be defined as solvable if you can add two empty rows on the top and bottom of the maze respectively to make it Mx(N+2) and there exists a path from the top row to the bottom row. This is more or less an informal definition, but very

For example, The maze given below is solvable

![A maze with solution](/assets/maze/solvable.png)
_There exists a path from the top to the bottom_

But the one below is not.
![A maze without solution](/assets/maze/unsolvable.png)
_No path is present_

It is trivial to come up with an algorithm for generating mazes that are always solvable. A straight line path from top row to bottom row is solvable by definition, however we’re not interested in that, so our definition of mazes needs to be more tricky.

## Definition for an Interesting maze

As mentioned, a maze which is just "Solvable" isn't of particular interest. It is very trivial to generate it and solve it. So I am going to add 2 more criteria for the generated maze. I came up with these criteria after a bit of reference on mazes[^5]

_1. The maze should be simply connected or perfect, i.e, it should have no loops and should have one and only one solution._

This means that the maze should both be solvable and not be very easily solvable (like a hallway of empty blocks). 

_2. The maze should have at least one dead-end_

A dead-end can be defines as an empty cell in the maze which is not the start or end cell and has only one path out of it. A maze without any dead-end will be a very easy one to solve, but instead, we want the maze to be challenging enough.

Now, I am defining an _Interesting Maze_ as a maze which satisfies both 1. and 2.

So our problem definition becomes

### Is it possible to come up with a maze generation algorithm which produces a solvable perfect maze with at least one dead-end^ using the 5 context bits (two bits to the left and three bits above)?

![](/assets/maze/context-bits.png)
_X is generated using the bit values of a, b, c, d and e._


## The Solution

Before approaching the solution, my intuition for the answer is "No", it is not possible to generate an Interesting maze with only using the given context-bits for generating the next bit.

### WIP



References:

[^1]: [List of unsolvable problems in Computer Science](https://en.wikipedia.org/wiki/List_of_unsolved_problems_in_computer_science)
[^2]: [Atari 2600](https://en.wikipedia.org/wiki/Atari_2600)
[^3]: [Interview with Paul Allen Newell](https://www.digitpress.com/library/interviews/interview_paul_allen_newell.html)
[^4]: [An archaeological examination of an Atari 2600 game](https://arxiv.org/ftp/arxiv/papers/1811/1811.02035.pdf)
[^5]: [Maze Algorithms](https://datagenetics.com/blog/november22015/index.html)
