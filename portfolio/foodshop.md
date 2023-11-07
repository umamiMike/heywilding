---
author: "Mike Wilding"
date: "2022-09-06 20:06:09"
categories:
- Write Up
tags:
title: "Foodshop"
description: ""
draft: false
---



## Why I Made This

All of my software experience was related to enterprise codebases where I was primarily creating things on the backend. 
All the work I had done wasnt publicly available. I wanted to demonstrate that I could build a front-end application client from scratch using modern Javascript, TailwindCSS, and Typescript.

I took a prompt from looking at DoorDash.

I wanted to work with a user story (order a burrito from a shop) that I hadn't worked with prior, and was something many other people have used.

## Implementation Notes

### Designing the App

Having never made a food cart app, I first clicked through DoorDash, creating a [mindmap](/images/portfolio/BurritoComponents.jpg)  (only the components portion is shown) to identify and clarify the structure and naming conventions, and to tease out what commands, events, and data structures would be needed.

### Handling the state of the application in a sane way

To manage the state of the application, I used the useReducer and useContext hooks as they are already built into React and using more is not required yet.

### Implementing Typescript

Managing Data Types is important[^1]
After the happy path was done, I was running into some technical debt I wanted cleaned up, so I implemented Typescript and ESlint.  This changed the application a lot (for the better).


## Where To From Here 

I had some thoughts about what I might do going forward

### Moving Toward Event Driven Software

I have been interested in using an [Event Driven](https://en.wikipedia.org/wiki/Event-driven_architecture) pattern for some time and thought this would be a good "trivial" use case.

### Actually use the GraphQL meaningfully

As a part of my first draft I partially implemented a client/server communication  GraphQL  event sourced communication layer, with an Elixir backend.  This will allow the ability to store the state of the application at any time, and would facilitate further expanded feature set with greater ease.

## Tools Used

Javascript, Typescript, GraphQL, Elixir, TailwindCSS, ESLint
[^1]:  NASA’s Mars Climate Orbiter project famously crashed due to a mixup in the units being used. The compiler did not complain because all the numbers involved were typed as floating point numbers, and you are permitted to manipulate them as you please. However, the Orbiter failure should be seen as a typing failure. [link to full article](https://academiccomputing.wordpress.com/2013/10/17/the-importance-of-types/) 

##  Links
- [link to the repo](https://github.com/umamiMike/burrito-demo)