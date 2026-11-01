---
title: "Evals"
type: explainer
line: "A structured test of how well an AI system does its job. Not a unit test: it expects some misses and aims at the ways your system fails."
topic: "Building with AI"
tags: [evals, testing, quality]
aliases: ["eval", "evaluation", "AI evals"]
related: []
updated: 2026-11-01
---

# Evals

_A structured test of how well an AI system does its job. Not a unit test: it expects some misses and aims at the ways your system fails._

An eval is a structured test of how well your AI system does what matters: quality, reliability, accuracy
([AI Engineer, 6:52](https://www.youtube.com/watch?v=bk0TmxoZlUY&t=412s)). It has three parts ([AI Engineer, 5:39](https://www.youtube.com/watch?v=FB-MLPhL9Ms&t=339s)):

- **A task:** the [agent](ai-agent.md) or prompt under test.
- **A dataset:** example inputs that start the task.
- **Scorers:** checks that grade each result.

A scorer can be code, or another model that grades, an LLM as judge ([AI Engineer, 7:40](https://www.youtube.com/watch?v=bk0TmxoZlUY&t=460s)). See also Agent engineering.

## Why it is not a unit test

A unit test is a small code check. One engineer at an eval platform says unit tests are exhaustive, but evals start
from the agent's main failure modes, the ways it tends to go wrong. You or an expert name them. Listing everything
that could go wrong is endless ([AI Engineer, 3:47](https://www.youtube.com/watch?v=FB-MLPhL9Ms&t=227s), [4:41](https://www.youtube.com/watch?v=FB-MLPhL9Ms&t=281s)).

An engineer at a coding-tool company says why: 95% of an AI app is ordinary code that works every time, and tests cover it.
The crucial 5% is where it can fail ([AI Engineer, 4:34](https://www.youtube.com/watch?v=L8OoYeDI_ls&t=274s)).

## What it is not

- **Not exact.** The eval platform's engineer says results can be directional. If the trend is right, a judge that is not perfect is fine ([AI Engineer, 4:41](https://www.youtube.com/watch?v=FB-MLPhL9Ms&t=281s)).
- **Not only a guard.** Another engineer at that platform relays a colleague's view: evals let you play offense and build rigorously, not
  only defend ([AI Engineer, 3:15](https://www.youtube.com/watch?v=bk0TmxoZlUY&t=195s), [4:22](https://www.youtube.com/watch?v=bk0TmxoZlUY&t=262s)).
- **Not only before launch.** Offline evals run before release. Online evals watch the live app ([AI Engineer, 8:34](https://www.youtube.com/watch?v=bk0TmxoZlUY&t=514s)).

## Scores that mislead

- **Perplexity** is how many words the model hesitates between at each step. Builders still watch it, but academic tests dropped it, since it depends on the tokenizer and the data ([Stanford Online, 19:07](https://www.youtube.com/watch?v=9vM4p9NN0Ts&t=1147s), [20:51](https://www.youtube.com/watch?v=9vM4p9NN0Ts&t=1251s)).
- **The same test, run differently.** A Stanford lecturer says one model scored 63.7 on one run of a test and 48.8 on another ([Stanford Online, 26:04](https://www.youtube.com/watch?v=9vM4p9NN0Ts&t=1564s)).
- **Contamination.** The test may sit in the training text. Outsiders cannot see what was trained on ([Stanford Online, 26:04](https://www.youtube.com/watch?v=9vM4p9NN0Ts&t=1564s), [27:37](https://www.youtube.com/watch?v=9vM4p9NN0Ts&t=1657s)).

First set: Your first set of evals.

Tests built from your own work: Bench from your own work.

## Sources

- [Evals 101 — Doug Guthrie, Braintrust](https://www.youtube.com/watch?v=bk0TmxoZlUY), AI Engineer, 2025-06-27
- [The maturity phases of running evals — Phil Hetzel, Braintrust](https://www.youtube.com/watch?v=FB-MLPhL9Ms), AI Engineer, 2026-05-27
- [Evals Are Not Unit Tests — Ido Pesok, Vercel v0](https://www.youtube.com/watch?v=L8OoYeDI_ls), AI Engineer, 2025-08-06
- [Stanford CS229 I Machine Learning I Building Large Language Models (LLMs)](https://www.youtube.com/watch?v=9vM4p9NN0Ts), Stanford Online, 2024-08-27
