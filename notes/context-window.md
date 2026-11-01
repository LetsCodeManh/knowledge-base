---
title: "Context window"
type: explainer
line: "Everything an AI model can see at once. It has a limit, it costs tokens, and clutter in it makes answers worse."
topic: "AI basics"
tags: [context, tokens]
aliases: ["context"]
related: []
updated: 2026-10-27
---

# Context window

_Everything an AI model can see at once. It has a limit, it costs tokens, and clutter in it makes answers worse._

The context window is everything an AI model can see at one time: its instructions, your messages and its answers,
counted in [tokens](token.md). Every model has a limit on how many tokens it can see at once ([Matt Pocock, 0:12](https://www.youtube.com/watch?v=9P36wMntNSI&t=12s)).

Why a chat seems to remember: How a chat remembers.

## Why it matters

- **It has a size.** Small models running on your own machine have smaller ones. In one test a local model did not quite
  sum up each of several articles in two sentences, and the creator put it down to its smaller window
  ([NetworkChuck, 16:28](https://www.youtube.com/watch?v=ONgECvZNI3o&t=988s)).
- **Clutter wastes it.** Information the task does not need still fills the window ([Claude, 22:55](https://www.youtube.com/watch?v=mWvtOHlZM-I&t=1375s)).
- **Longer means vaguer.** Each token has a fixed amount of attention to share, so more context spreads it thinner. The dictionary calls this attention degradation ([Matt Pocock, Attention budget](https://github.com/mattpocock/dictionary-of-ai-coding#:~:text=Attention%20budget), [Attention degradation](https://github.com/mattpocock/dictionary-of-ai-coding#:~:text=Attention%20degradation)). It names a "smart zone" early in a session and a "dumb zone" later. The dictionary says that on frontier models, the newest and most capable ones, the dumb zone commonly begins around 125K to 150K tokens, though this is debated ([Matt Pocock, Smart zone](https://github.com/mattpocock/dictionary-of-ai-coding#:~:text=Smart%20zone)).
- **Where the dumb zone starts.** A teacher of AI coding says the decline is gradual. Where it begins depends on the model and probably the task. Their guideline is about 150,000 tokens, up from about 100,000 six months earlier ([Matt Pocock, 0:00](https://www.youtube.com/watch?v=sOd7svdu_1I&t=0s), [1:24](https://www.youtube.com/watch?v=sOd7svdu_1I&t=84s)). If the model makes up facts, especially about data (a [Hallucination](hallucination.md)), the teacher says you are probably in it ([Matt Pocock, 1:24](https://www.youtube.com/watch?v=sOd7svdu_1I&t=84s)).
- **A new chat empties it.** An AI researcher says to start a new chat because a long window can distract the model ([Andrej Karpathy, 16:20](https://www.youtube.com/watch?v=EWvNQjAaOHw&t=980s)). See Using a chat app well.
- **It costs.** Size is counted in tokens, and fewer tokens means a lower bill ([Claude, 34:47](https://www.youtube.com/watch?v=mWvtOHlZM-I&t=2087s)). In a demo
  an [agent](ai-agent.md) used over 200,000 tokens for one task. Once it could write and run code to go through the data, instead of
  reading all of it, the count fell sharply ([Claude, 33:46](https://www.youtube.com/watch?v=mWvtOHlZM-I&t=2026s)).

## How to keep it clean

- Break a task into small parts and run each in a fresh window. The same teacher finds this spends fewer tokens for better results ([Matt Pocock, 0:00](https://www.youtube.com/watch?v=sOd7svdu_1I&t=0s)). Past the dumb zone, clear the context, compress it, pass the task on, or change the workflow ([Matt Pocock, 1:24](https://www.youtube.com/watch?v=sOd7svdu_1I&t=84s)).
- Load know-how only when needed: Skills cost 30 to 50 tokens each until used ([Anthropic, 0:30](https://www.youtube.com/watch?v=fOxC44g8vig&t=30s)).
- Send side jobs to a subagent: it has its own context window ([Anthropic, 2:05](https://www.youtube.com/watch?v=fOxC44g8vig&t=125s)).
- Leave the System prompt only for what the model needs whatever the task, as Anthropic's engineer advises ([Claude, 22:04](https://www.youtube.com/watch?v=mWvtOHlZM-I&t=1324s)).
- Watch the MCP servers you connect: Anthropic's engineer names the room they take as a drawback ([Claude, 32:48](https://www.youtube.com/watch?v=mWvtOHlZM-I&t=1968s)).

Choosing what goes in, step by step: Context engineering.

## Sources

- [Stop stuffing your context window (here's why)](https://www.youtube.com/watch?v=9P36wMntNSI), Matt Pocock, 2025-09-23
- [You NEED to Use n8n RIGHT NOW!! (Free, Local, Private)](https://www.youtube.com/watch?v=ONgECvZNI3o), NetworkChuck, 2025-07-16
- [Tool, skill, or subagent? Decomposing an agent that outgrew its prompt](https://www.youtube.com/watch?v=mWvtOHlZM-I), Claude, 2026-05-23
- [AI Coding Dictionary](https://github.com/mattpocock/dictionary-of-ai-coding), Matt Pocock, 2026-09-24
- [What is the dumb zone?](https://www.youtube.com/watch?v=sOd7svdu_1I), Matt Pocock, 2026-07-20
- [How I use LLMs](https://www.youtube.com/watch?v=EWvNQjAaOHw), Andrej Karpathy, 2025-02-27
- [Claude Agent Skills Explained](https://www.youtube.com/watch?v=fOxC44g8vig), Anthropic, 2025-11-26
