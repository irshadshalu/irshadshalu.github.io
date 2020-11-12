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



Starting with an empty Svelte project was way easier than I imagined. I started with the sveltejs/template and used [degit](https://github.com/Rich-Harris/degit) for project scaffolding as recommended.

```bash
npx degit sveltejs/template project-name
cd project-name
```

And then install and run using

```bash
npm install
npm run dev
```

Phew, that just went good!

![Svelte Is Ready Terminal](/assets/svelte-is-ready.png)


![Svelte Hello World](/assets/svelte-hello-world.png)


I like it when things just work without having to go on _stackoverflow treasure hunt_ to fix things.


Time to learn something solid: https://svelte.dev/tutorial/basics 

* An application is composed of one or more **Components**.
* **Components** are reusable block of code which contains HTML, CSS and JS that belong together in a .svelte file. -> _that's pretty neat. I don't have to write 3 different files for every component!_
* `<style>` contains all CSS. `<script>` contains all JS and the rest is HTML
* Variable names in JS can just be used directly with `{varName}`, when the value changes, the value in the page changes as well. -> _This means no more this.refresh() or this.setValue() calls. I already like this a lot._
* `<img {src} alt="A man dances.">` Just works when src is an image reference. I don't even have to provide `src={src}`. -> _Ok, maybe that's a bit too much for shorthanding? do I hate it? No._
* Whatever CSS that I add is scoped only to the component! It won't affect rest of the component. -> _I can safely mess with CSS and expect the whole page to not break now_
* Use `import Nested from './Nested.svelte';` to import other components and use them.
* Use the `$: name = firstName + lastName;` syntax to make sure name is reactive and gets updated whenever firstName/lastName changes! `$` here is a JavaScript label which says execute this statement whenever any of the values are updated which is pretty neat. (another usecase will be to log a value whenever it changes!)

I learned a bit more, but writing it all out here will be boring for me and anyone who is reading this. So I recommend you to try it out yourself.

## Hour 1 - I still don't know much of Svelte, but I will. This is cool!



