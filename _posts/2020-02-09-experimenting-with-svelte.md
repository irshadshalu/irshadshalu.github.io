---
layout: post
title:  "Experimenting with Svelte - A Journal"
date:   2020-02-09 04:44:48 +0530
categories: web svelte
---

It's a good bright sunday, I had a nice lunch, took a short nap and now back infront of the laptop - bored and thinking of doing something productive. 

That's when I remembered [**Svelte**](https://svelte.dev/); the super awesome brand new web frontend framework with the tagline `Cybernetically enhanced web apps`. 



I wanted to check it out and see what all the fuss is about. I decided to blog about the experience in a live fashion and I will be writing this as I go. 


_Will I find it amazing? or will I hate it?, Will I even get time to try it out properly and actually complete this journal?, let's find out!_


## Hour 0 - I don't know Svelte at all. 


I opened https://svelte.dev, And the main selling points were


* Write less code - _Boilerplate-free components._ Ah, like most other framework promises, but fails to deliver? let's see...

* No virtual DOM - _Svelte compiles to vanilla JavaScript._ Wait, that is actually quite interesting. I definitely wanna see it in action. 

* Truly reactive - _No complex state management libraries, reactivity within JavaScript._ Nice. I have always been a fan of less dependencies. 


Enough talk, let's dive into some Hello World!. 



## Hour 1 - I still don't know much of Svelte, but I will. This is cool!

Starting with an empty Svelte project was way easier than I imagined. I started with the sveltejs/template and used [degit](https://github.com/Rich-Harris/degit) for project scaffolding as recommended.

```
	npx degit sveltejs/template project-name
	cd project-name
```

And then install and run using

```
npm install
npm run dev
```

Phew, that just went good!

![Svelte Is Ready Terminal](assets/svelte-is-ready.png)


![Svelte Hello World](assets/svelte-hello-world.png)


I like it when things just working without having to go on stackoverflow treasure hunt to fix things.




