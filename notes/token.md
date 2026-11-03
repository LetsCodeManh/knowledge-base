---
title: "Token"
type: explainer
line: "The small piece of text an AI model reads and writes, and the unit its price and limits are counted in."
topic: "AI basics"
tags: [tokens, pricing, context]
aliases: ["tokens"]
related: []
updated: 2026-11-01
---

# Token

_The small piece of text an AI model reads and writes, and the unit its price and limits are counted in._

A token is a small chunk of text, the piece an AI model reads and writes instead of whole words. It is also the unit
AI companies use to set their prices and limits ([Better Stack, 0:45](https://www.youtube.com/watch?v=ZTmZOdB5o0U&t=45s)).

## What a token is

- **A chunk, not a letter or a word.** One explainer says the text you send is split into chunks, each with its own
  ID number. A common word like "the" gets one token. A rarer word like "unbelievable" splits into pieces, "un",
  "believe" and "able" ([Better Stack, 0:45](https://www.youtube.com/watch?v=ZTmZOdB5o0U&t=45s)).
- **Roughly three quarters of a word.** That is the same explainer's average ([Better Stack, 0:45](https://www.youtube.com/watch?v=ZTmZOdB5o0U&t=45s)).
- **Splitting is done by a tokenizer.** The model does not read text directly, only tokens ([Better Stack, 0:45](https://www.youtube.com/watch?v=ZTmZOdB5o0U&t=45s)).
  Your text is broken into tokens and passed through the model, and text comes out ([KodeKloud, 0:00](https://www.youtube.com/watch?v=kIlgDm5gcMY&t=0s)).

## Why everything is counted in them

- **Price.** A reviewer put the price of Fable at $10 per million tokens in and $50 per million tokens out
  ([Theo - t3․gg, 9:33](https://www.youtube.com/watch?v=U3uX115I9sY&t=573s)).
- **Input and output differ.** Input tokens are billed at a lower rate than output tokens ([Matt Pocock, Input tokens](https://github.com/mattpocock/dictionary-of-ai-coding#:~:text=Input%20tokens)). Cached input costs less still ([Anthropic, Check cache performance](https://code.claude.com/docs/en/prompt-caching#:~:text=Check%20cache%20performance)).
- **Size of the [Context window](context-window.md).** The same reviewer says another model's cheap price holds only under 200,000
  tokens of room, and that it goes up to 500,000 ([Theo - t3․gg, 9:33](https://www.youtube.com/watch?v=U3uX115I9sY&t=573s)).
- **Fewer tokens, lower bill.** In a demo on Anthropic's channel, an AI helper used over 200,000 tokens for one task. After a change it
  used far fewer, and the cost fell with them ([Claude, 33:46](https://www.youtube.com/watch?v=mWvtOHlZM-I&t=2026s), [34:47](https://www.youtube.com/watch?v=mWvtOHlZM-I&t=2087s)).
- **Waste is money.** Tokens an AI tool spends on things it did not need are real money and use up room in the
  context window ([IBM Technology, 7:12](https://www.youtube.com/watch?v=g9JIUM0MHgQ&t=432s)). One video's test found the same data took 2,350 tokens written
  as JSON, a common text format ([Matt Pocock, 0:00](https://www.youtube.com/watch?v=YjPD9Alf1co&t=0s)), and about 1,200 in a plainer layout
  ([Matt Pocock, 1:02](https://www.youtube.com/watch?v=YjPD9Alf1co&t=62s)).

## Where to go next

**Spend fewer tokens**

- Cached input costs less than fresh input: Prompt caching ([Anthropic, Check cache performance](https://code.claude.com/docs/en/prompt-caching#:~:text=Check%20cache%20performance)).
- A commentator says Amazon and Meta shut their leaderboards of staff token use: Valuemaxxing ([ZAUEY (Claire Zau), 0:00](https://www.youtube.com/watch?v=msSZZenByJw&t=0s)).

**See the limit tokens set**

- The room a model has, counted in tokens: [Context window](context-window.md) ([Theo - t3․gg, 9:33](https://www.youtube.com/watch?v=U3uX115I9sY&t=573s)).

**Go below tokens**

- A model that reads single letters instead of tokens: Byte model.

## Sources

- [What Really Happens Inside ChatGPT (AI Explained)](https://www.youtube.com/watch?v=ZTmZOdB5o0U), Better Stack, 2026-10-07
- [Why do we need AI Agents when we have AI models?](https://www.youtube.com/watch?v=kIlgDm5gcMY), KodeKloud, 2026-08-24
- [Oh no (the new Grok model is good)](https://www.youtube.com/watch?v=U3uX115I9sY), Theo - t3․gg, 2026-07-09
- [AI Coding Dictionary](https://github.com/mattpocock/dictionary-of-ai-coding), Matt Pocock, 2026-09-24
- [How Claude Code uses prompt caching](https://code.claude.com/docs/en/prompt-caching), Anthropic, 2026-10-25
- [Tool, skill, or subagent? Decomposing an agent that outgrew its prompt](https://www.youtube.com/watch?v=mWvtOHlZM-I), Claude, 2026-05-23
- [CLI vs MCP: How AI Agents Choose the Right Tool for the Job](https://www.youtube.com/watch?v=g9JIUM0MHgQ), IBM Technology, 2026-05-04
- [Passing JSON to an LLM is SUPER wasteful](https://www.youtube.com/watch?v=YjPD9Alf1co), Matt Pocock, 2025-09-23
- [Goodbye Tokenmaxxing, Hello Valuemaxxing](https://www.youtube.com/watch?v=msSZZenByJw), ZAUEY (Claire Zau), 2026-06-05
