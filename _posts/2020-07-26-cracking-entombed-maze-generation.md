---
layout: post
title:  "An Attempt to Crack the Entombed Maze Generation Algorithm"
description: Attempting to solve what I thought was an interesting challenge only to find out it was not. So I proposed a new challenge.
date:   2020-07-25 21:12:04 +0530
categories: code study puzzle
---

_Work in Progress_

So I came across this problem in the List of unsolved problems in computer science - Wikipedia[^1] on a boring Saturday evening when I was randomly browsing the web.

## A bit of background

Entombed is an  Atari 2600[^2] game released in 1982.  The game has a very simple gameplay.  Try out the game here: [Entombed](https://www.retrogames.cz/play_1044-Atari2600.php?language=EN)

There’s a vertically scrolling maze (which is also symmetric) and player has to go through the maze avoiding enemies and picking up make-break boosters (which are useful for making a wall or breaking one)

The game has been subject to academic research particularly for its maze generation. Since the Atari 2600 had a limited ROM size, the mazes were too big to store on the ROM, and after researchers evaluated[^4] the game’s ROM, they found that the mazes were generated during runtime.



## Defining the problem

The mazes that were produced in the game were unsolvable without efficient use of the make-break item (Which adds the game factor to it). However, during an interview with the Paul Allen Newell who previously worked on the game, it is said that they were able to come up with an algorithm which consistently generates solvable mazes in the interview with Paul Allen Newell[^3]

> The story of the algorithm is that one night after work, Duncan and I went out for a beer and ended up coming up with this “problem” of wondering whether one could generate an endless maze that always had a solution.  At the time, we weren’t thinking of a game per se, it just seemed like an interesting puzzle for us to solve.  We worked out the algorithm and, since I knew how to program a VCS system (Duncan was Vectrex only), I spent a weekend coding something up.  We were surprised at the elegance of the algorithm as it gave us the ability to dial in a “difficulty factor” (via a bit setting) and we could prove that there was not only a point where it became unsolvable

_(Here, “VCS" refers to Atari Video Computer System and not Version Control System)_

So the question I was actually interested in is

### Is it possible to come up with a maze generation algorithm which only produces a solvable maze using the 5 context bits (two bits to the left and three bits above)?


Simply upon inspection, we can see that the maze that is generated within the game itself is unsolvable. Although the title of this post is about Entombe and it's mazes, we're past that and I am starting to question why this problem is even on the list of unsolvable problems[^1]. The maze generated isn't solvable and not special except for the aesthetics of it. A reddit thread about this in /r/programming seems to agree with me[^6], which sadly I stumbled upon only after spending enough time on this.

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


## Attempting a solution

Before approaching the solution, my intuition for the answer is "No", it is not possible to generate an Interesting maze with only using the given context-bits for generating the next bit.

Take P to be our initial Conjecture

P: _It is possible to construct a vertically scrolling perfect maze with at least one dead-end using the cell values of previous two blocks in the same row and left, middle and right cells on the row above it_

Assume our generated maze Z has a thick wall with two cells width on either sides (This doesn't affect our original conjecture since adding solid walls on sides will not interfere with the original solution) 

Ehhm... Waitt!!

As I was trying this out in paper to order to prove it, I actually was able to come up with a configuration that generates a perfect maze (with only one path and no loops) and with more than one dead-ends, although it doesn't look very _challenging_, it does satisfy all the criteria and it is trivial to show that the maze will satisfy these conditions (Since no random selection is involved). [Here](https://codesandbox.io/s/solitary-microservice-6j1zk?file=/src/index.tsx) is the configuration for those who are interested (You might want to toggle the first row to something like 1, 1, 0, 1, 1, 1, 1, 1, ...)


![A maze which is perfect and has dead-ends](/assets/maze/silly_maze.png)
_Well, that was a bit disappointing_

And even adding some randomness makes the maze a bit better, but still kinda not challenging.

Here, the ? indicates bits which are randomly chosen.

![This maze looks a bit more interesting at least](/assets/maze/somewhat_okay_maze.png)
_At least this one is a little bit better_


Following are the rules used for this particular maze

			00110 - 1
			00111 - 0
			01000 - R
			01011 - 1
			01100 - 1
			01101 - 0
			10000 - 1
			10001 - 1
			10010 - 1
			10011 - 0
			11000 - 1
			11001 - 1
			11011 - 1
			11100 - 0
			11101 - 0




Okay, but this is not what I want, I want a maze that is challenging as well, and something that could be randomized although not strictly a requirement at the moment. So it's time to re-define our "Interesting Maze" a little bit more so that it actually is interesting!

_Work in Progress_




References:

[^1]: [List of unsolvable problems in Computer Science](https://en.wikipedia.org/wiki/List_of_unsolved_problems_in_computer_science)
[^2]: [Atari 2600](https://en.wikipedia.org/wiki/Atari_2600)
[^3]: [Interview with Paul Allen Newell](https://www.digitpress.com/library/interviews/interview_paul_allen_newell.html)
[^4]: [An archaeological examination of an Atari 2600 game](https://arxiv.org/ftp/arxiv/papers/1811/1811.02035.pdf)
[^5]: [Maze Algorithms](https://datagenetics.com/blog/november22015/index.html)
[^6]: [The mysterious maze generating code hidden in an early video game](https://www.reddit.com/r/programming/comments/d8kk03/the_mysterious_maze_generating_code_hidden_in_an/)
