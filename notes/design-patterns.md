---
title: "Design patterns"
type: explainer
line: "Named, reusable ways to solve problems that keep coming up in code. Ten of the best known, in a line each, and when not to use them."
topic: "Programming"
tags: [patterns, javascript, typescript, object-oriented]
aliases: ["software design patterns", "gang of four", "GoF patterns"]
related: []
updated: 2026-11-01
---

# Design patterns

_Named, reusable ways to solve problems that keep coming up in code. Ten of the best known, in a line each, and when not to use them._

A design pattern is a named, reusable way to solve a problem that programmers meet again and again. The best-known collection is a book by four C++ engineers, the Gang of Four, with 23 patterns ([Fireship, 0:00](https://www.youtube.com/watch?v=tv-_1er1mWI&t=0s)).

They fall into three groups: creational (how objects are made), structural (how objects relate) and behavioral (how objects communicate) ([Fireship, 0:00](https://www.youtube.com/watch?v=tv-_1er1mWI&t=0s)).

A pattern is not an algorithm. You cannot paste one from a forum; you have to think to apply it. Used in the wrong place, it adds complexity and boilerplate ([Fireship, 1:00](https://www.youtube.com/watch?v=tv-_1er1mWI&t=60s)).

## Why learn them

A teacher says small programs of 50 or 100 lines hide the problem. In a code base of tens of thousands of lines, you must know how pieces fit together. Then you will not rewrite thousands of lines later ([Tech With Tim, 0:00](https://www.youtube.com/watch?v=6dsuowZVv6Q&t=0s)).

## Ten patterns, in a line each

- **Singleton:** an object that can be created only once. In JavaScript a plain global object does the same job ([Fireship, 1:34](https://www.youtube.com/watch?v=tv-_1er1mWI&t=94s)).
- **Prototype:** make a new object by cloning one that already exists ([Fireship, 2:24](https://www.youtube.com/watch?v=tv-_1er1mWI&t=144s)).
- **Builder:** build an object step by step with chained method calls ([Fireship, 3:46](https://www.youtube.com/watch?v=tv-_1er1mWI&t=226s)).
- **Factory:** a function decides which object to create, so the choice is made in one place ([Fireship, 4:23](https://www.youtube.com/watch?v=tv-_1er1mWI&t=263s)).
- **Facade:** one simple interface that hides several complicated parts ([Fireship, 4:54](https://www.youtube.com/watch?v=tv-_1er1mWI&t=294s)).
- **Proxy:** a stand-in that sits in front of an object. Vue uses one to notice when data changes and update the screen ([Fireship, 5:47](https://www.youtube.com/watch?v=tv-_1er1mWI&t=347s)).
- **Iterator:** a way to walk through a collection. You pull each item in turn ([Fireship, 6:45](https://www.youtube.com/watch?v=tv-_1er1mWI&t=405s)).
- **Observer:** many listeners subscribe to one source, and it pushes each change to all of them ([Fireship, 7:47](https://www.youtube.com/watch?v=tv-_1er1mWI&t=467s)).
- **Mediator:** a middleman that stops many objects from talking to each other directly. Express's middleware is one ([Fireship, 8:58](https://www.youtube.com/watch?v=tv-_1er1mWI&t=538s)).
- **State:** an object hands its work to a separate class for each state, in place of long if or switch chains ([Fireship, 9:50](https://www.youtube.com/watch?v=tv-_1er1mWI&t=590s)).

## When not to use one

Lean on your language's built-in features before reaching for a pattern, the presenter says ([Fireship, 1:34](https://www.youtube.com/watch?v=tv-_1er1mWI&t=94s)). The book has many critics ([Fireship, 1:00](https://www.youtube.com/watch?v=tv-_1er1mWI&t=60s)).

See also Keep a system simple, Programmer regrets, UML diagrams and TanStack Charts.

## Sources

- [10 Design Patterns Explained in 10 Minutes](https://www.youtube.com/watch?v=tv-_1er1mWI), Fireship, 2022-03-14
- [Learning Programming Design Patterns](https://www.youtube.com/watch?v=6dsuowZVv6Q), Tech With Tim, 2023-04-07
