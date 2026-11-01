---
title: "Hallucination"
type: explainer
line: "When an AI states something false with confidence. Two kinds, two different fixes: give it the facts, or give it less to read."
topic: "AI basics"
tags: [hallucination, accuracy, context]
aliases: ["AI makes things up", "AI hallucinations", "confabulation"]
related: []
updated: 2026-10-26
---

# Hallucination

_When an AI states something false with confidence. Two kinds, two different fixes: give it the facts, or give it less to read._

A hallucination is when an AI makes something up and says it with confidence ([Austin Marchese, 5:10](https://www.youtube.com/watch?v=7zZy1QTvokM&t=310s)). One coding teacher says hallucinations are inevitable and probably
come with how these models work ([Matt Pocock, 0:00](https://www.youtube.com/watch?v=H-JHumbpORI&t=0s)).

## Why it happens

A model is not a database that looks facts up. The teacher compares it to a fuzzy JPEG of human knowledge: it knows the general shape
of things but cannot name the exact details ([Matt Pocock, 0:00](https://www.youtube.com/watch?v=H-JHumbpORI&t=0s)).

## Two kinds

The teacher sorts them by one question: was the information in the [Context window](context-window.md) ([Matt Pocock, 0:00](https://www.youtube.com/watch?v=H-JHumbpORI&t=0s), [0:47](https://www.youtube.com/watch?v=H-JHumbpORI&t=47s))?

1. **It was not there.** The model tried to recall something you never gave it, and failed. The teacher calls this a
   hallucination of factuality, and says never to trust a model without sources. The fix: put the information in the
   context ([Matt Pocock, 0:00](https://www.youtube.com/watch?v=H-JHumbpORI&t=0s), [0:47](https://www.youtube.com/watch?v=H-JHumbpORI&t=47s)). For the habit of giving facts, see Prompting basics.
2. **It was there, but the answer is still wrong.** The teacher calls this a hallucination of fidelity, sometimes from
   [attention degradation](context-window.md): the longer the context, the more strained the links between its parts. The fix: put fewer [tokens](token.md) in
   it, by clearing the context, compressing it or handing the task to a fresh session ([Matt Pocock, 0:47](https://www.youtube.com/watch?v=H-JHumbpORI&t=47s)).

RAG automates loading the facts: it adds the facts it finds to your question, so the model can use them instead of guessing ([IBM Technology, 3:48](https://www.youtube.com/watch?v=zYGDpG-pTho&t=228s)).

An AI researcher calls what a model writes without sources dreaming: an invented ISBN number looks reasonable but almost certainly does not exist ([Andrej Karpathy, 8:58](https://www.youtube.com/watch?v=zjkBMFhNj_g&t=538s)). The researcher adds that further training does not fix this. It only directs the dreams into helpful assistant dreams ([Andrej Karpathy](https://www.youtube.com/watch?v=zjkBMFhNj_g)).

A computer science professor says a model plays a word-guessing game: it writes text that fits the request, with no model of what a legal citation is ([Chris Williamson, 43:29](https://www.youtube.com/watch?v=TnK1gkoeH4E&t=2609s), [44:32](https://www.youtube.com/watch?v=TnK1gkoeH4E&t=2672s)). In one case, five lawyers were sanctioned after a chatbot invented case law they did not check ([Chris Williamson, 43:29](https://www.youtube.com/watch?v=TnK1gkoeH4E&t=2609s)). The professor asked one for a public-domain quote and got an invented one, even when they asked again ([Chris Williamson, 44:32](https://www.youtube.com/watch?v=TnK1gkoeH4E&t=2672s), [46:04](https://www.youtube.com/watch?v=TnK1gkoeH4E&t=2764s)).

## Learned or given

What a model learned in training is frozen and blurs on rare facts. What sits in the context is read directly and hallucinates less ([Matt Pocock, Parametric knowledge](https://github.com/mattpocock/dictionary-of-ai-coding#:~:text=Parametric%20knowledge), [Contextual knowledge](https://github.com/mattpocock/dictionary-of-ai-coding#:~:text=Contextual%20knowledge)). So a library newer than the model's knowledge cutoff, where its training data ends, is a trap: load its docs ([Matt Pocock, Knowledge cutoff](https://github.com/mattpocock/dictionary-of-ai-coding#:~:text=Knowledge%20cutoff)).

## What does not help

Shouting at the model, pleading or just saying "do better" will not necessarily help, one creator says. The lever that creator names is verification of results: define in advance what a good result is, and have it checked ([Evals](evals.md))
([Austin Marchese, 5:10](https://www.youtube.com/watch?v=7zZy1QTvokM&t=310s), [6:06](https://www.youtube.com/watch?v=7zZy1QTvokM&t=366s)).

## Sources

- [Stop Prompting Claude. Use Karpathy's Method Instead.](https://www.youtube.com/watch?v=7zZy1QTvokM), Austin Marchese, 2026-06-09
- [My agent hallucinated - what do I do?](https://www.youtube.com/watch?v=H-JHumbpORI), Matt Pocock, 2026-07-15
- [RAG vs Fine-Tuning vs Prompt Engineering: Optimizing AI Models](https://www.youtube.com/watch?v=zYGDpG-pTho), IBM Technology, 2025-04-14
- [(1hr Talk) Intro to Large Language Models](https://www.youtube.com/watch?v=zjkBMFhNj_g), Andrej Karpathy, 2023-11-23
- [The Future Belongs to People Who Think Like This - Cal Newport](https://www.youtube.com/watch?v=TnK1gkoeH4E), Chris Williamson, 2026-03-05
- [AI Coding Dictionary](https://github.com/mattpocock/dictionary-of-ai-coding), Matt Pocock, 2026-09-24
