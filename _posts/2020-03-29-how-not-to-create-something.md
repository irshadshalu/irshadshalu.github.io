---
layout: post
title:  "How NOT To Create Something"
date:   2020-03-29 20:24:04 +0530
categories: lifestyle code 
---

![My Mac](/assets/mac_doodle.png)

## The Crisis

It's 29th of March, 2020. India has been under a nationwide lockdown since 25th to contain the Covid-19 Pandemic.

Even before the lockdown, we were given work from home for the entire week and I kind of knew this was going to come. I wanted to create something in my free time (As I am going to have too much of it.).


Before all of this happened, I've been busy trying to learn Algorithms, Data Structures and get better at solving programming questions. I had put up daily goals and were successfully completing them in a streak. But this all stopped when I started the plan to "make" something. 

## What am I Going to Make?

I had few ideas. One of them was an idea to make a game that's similar to the popular "Psych by Ellen"[^1] game, but with some additional features and UI/UX improvements to make it a lot better (I'm sorry Psych devs, the idea is brilliant, but the implementation can be a lot better). Also, the last time I tried to play Psych, they showed me a notifications which read along the lines of

> "We are getting too much load which is causing issues to the game servers. Please try again later if you have trouble creating game"


So yes. Among some other brilliant ideas, I chose this. This seems doable and could be nice too to have an open source version of it.


## Starting Off...

To be fair, I started off pretty well. I've been [trying to learn ruby on rails](https://github.com/irshadshalu/rails-first-project) and [Svelte](/2020-02-08/experimenting-with-svelte) for a while, so my initial idea was to pick rails as the backend and Svelte as the frontend. 

But no, I got off on the wrong foot with Ruby, too much issues and hiccups again and it didn't go as smooth as the first blog project (Because I'm a noob in Ruby/Rails, okay?. Don't Judge me!). But more because I was in a hurry. I wanted to see results fast.

I also didn't listen to a friend's advice on learning Rails slow and steady. I just wanted to make the thing; I wanted to see the results fast. (that maker instinct, you know?). 

So I did the next best thing. I used [Django](https://www.djangoproject.com/) for the backend and it was a smooth sail. Thanks to https://djangobuilder.io/, Creating models, creating REST APIs, authentication, everything was done within a day. I had also made the sequence diagram for entire game flow in [PlantUML](https://plantuml.com/sequence-diagram). Everything was going smooth. I was happy. 

## Life Gets Boring (And So Does Work)

Well, now I have a solid design, I know how to implement it. I know what to do next and that's when I got bored of it. So I did what any fullstack developer who gets bored of writing backend will do - I started doing the frontend for the game. 

Initially, my plan was to make it as a progressive web app that can be played by anyone anywhere from any device, and also open source - But these two will likely not provide a smooth gaming performance when the user wants to switch apps, or do something else, etc.. So then I decided to make it using the unofficial [Svelte-Native](https://svelte-native.technology/) framework. It again started off great, and again I got bored of writing code that I know how it's going to be (I don't know, maybe it's the isolation combined with lack of satisfaction doing this.)


## What Did I Do Next?

So I stopped. Yes, you read that right. **I quit**. I didn't want to make it anymore, I got tired of it. 

Don't get me wrong. I still think it's a great idea and something that can be made in a week or two, I just lack the motivation to do it anymore.

Remind you, I also had my day job (I usually spent 8+ hours on work every day, even if I'm working from home.) and I can't go out and life gets tiring pretty quick. So, I get a little time to spend on the project and spending these little time on a small pet project which you're no longer motivated in makes you question your life choices. 


So this is where I am right now. I quit and I'm back to learning Algorithms, Data Structures and solving competitive programming problems (Atleast that makes me feel satisfied when I see an AC submission :) )


## Footnotes 

### Everything gets boring. Sooner or later

Even if it's something you're truly passionate about, it might get boring at one point in your life. Give up or take a break. It's your choice

### Curse of knowledge slows you down (but in a good way though)

Back then when I was in college, making something was easy because I just wrote code as I went on. I didn't care about the maintainability/architecture/performance/testing concepts of the codebase. I just wrote code and it worked (quite Poorly, with a lot of bugs I had to fix later)

Now, after working with some of the best people in the industry for around 2 years, writing good quality/maintainable code with unit and integration tests, automated CI deployments, I can't just go back to writing code careless like I used to. I question every line that I write and every choices I make. I read documentation more than I used to and think about all the real life error scenarios that might happen. This all slows me down a lot, but fortunately, that does make my code a lot better and I feel satisfied at the end of the day about having it. 


### Give it time folks

Rome wasn't built in a day. Don't look for results within a day or two. This was a mistake that I did. I kept on rushing and I wanted to see results quick. Maybe, just maybe, if I was a little more patient - I would still be continuing the work (and not writing this blog at all)


### Take a break!


Yes I did take a break. I tried my hands on some doodling, a little bit of writing (all not worth sharing at the moment), and watching my favourite TV shows too. 


## What am I going to do next?

I don't know. Honestly, I have no clue. I don't even know what I'm going to have for lunch tomorrow; but if I knew, then that'd be less interesting right?, maybe it's the not-knowing part that makes our lives a little bit more interesting. You got some suggestions?


[^1]: Psych is a party game in which people can put up fake answers to  questions (which can be from a particular theme) and score points by making other people pick your made up answer. Except it really doesn't have to be a party game. You should be able to play it online with anyone across the world. 
