---
layout: '../../layouts/MarkdownProjectLayout.astro'
title: 'Vanilla To-Do'
author: 'kobijet'
shortDesc: 'A to-do list made with JS, HTML, and CSS'
longDate: 'November 11th, 2023'
pubDate: 11-11-2023
platforms: ["desktop"]
tags: ["web", "html", "css", "js"]
img:
    url: '/vanillatodo.jpg'
    alt: 'A to-do list web app'
    link: 'https://kobijet.github.io/todo-vanilla/'
---

### Links
[Live](https://kobijet.github.io/todo-vanilla/)
[Code](https://github.com/kobijet/todo-vanilla)

### Description
Vanilla To-Do is a minimal to-do list app I made using vanilla javascript, html, and CSS. The project is hosted on GitHub pages.

My primary objective for this project was to learn how JavaScript works to add dynamic content to static HTML and CSS websites. 

I knew the capabilities of frameworks like React and Vue, and the power they provided, but I wanted to better understand on a core level what was happening, before diving into those abstractions.

As a secondary objective, I wanted this to be a tool I could <em>actually</em> use. 

For these purposes, a simple to-do list as such will suffice. I decided I only needed one master list with all the tasks I need to get done and the capabilities to mutate the list, because I usually only keep a day's worth of tasks on my list at any time. If I need to plan beyond this, I want a bit more, like a calendar and Trello board.

### Features
* Uses LocalStorage to make tasks persistent across uses
* Extremely minimal, with only the bare essentials for a to-do list
    * Add new task
    * Complete task
    * Delete task
    * Edit task
    * Clear list
