---
title: "AI agent"
type: explainer
line: "An AI model that acts: it has tools and decides by itself which to use until the job is done."
topic: "Agents"
tags: [agents, tools]
aliases: ["agent", "agent loop"]
related: []
updated: 2026-11-01
---

# AI agent

_An AI model that acts: it has tools and decides by itself which to use until the job is done._

An AI agent is a model that can act, not only answer. It is given tools, such as files, web search and running code
([Claude, 25:55](https://www.youtube.com/watch?v=mWvtOHlZM-I&t=1555s)). In the example below, an agent chose which of its tools to use
([NetworkChuck, 25:45](https://www.youtube.com/watch?v=ONgECvZNI3o&t=1545s)).

## How it works

An agent perceives, reasons about the next step, acts, then observes the result and goes around again
([IBM Technology, 0:36](https://www.youtube.com/watch?v=VSFuqMh4hus&t=36s)). It is typically built on a Reasoning model ([IBM Technology, 1:27](https://www.youtube.com/watch?v=VSFuqMh4hus&t=87s)).

The model only writes a tool call as text; the software around it must run it
([Matt Pocock, Tool call](https://github.com/mattpocock/dictionary-of-ai-coding#:~:text=Tool%20call)). The software sends the result back, and the model reads it and decides: another tool call or a final answer ([Matt Pocock, Tool result](https://github.com/mattpocock/dictionary-of-ai-coding#:~:text=Tool%20result)). The model sees only what that software puts in front of it, its [Context window](context-window.md) ([Matt Pocock, Context window](https://github.com/mattpocock/dictionary-of-ai-coding#:~:text=Context%20window)).

In code, this is a message history, a step count and a `while` loop that calls the model each round ([Matt Pocock, 0:00](https://www.youtube.com/watch?v=VxDNUKw83PY&t=0s), [1:17](https://www.youtube.com/watch?v=VxDNUKw83PY&t=77s)).

## A small example

In n8n, the AI Agent node is a model with memory and tools. Asked "is the internet up?", it
chose to run its ping tools ([NetworkChuck, 24:52](https://www.youtube.com/watch?v=ONgECvZNI3o&t=1492s), [25:45](https://www.youtube.com/watch?v=ONgECvZNI3o&t=1545s)). Build one:
Your first AI agent in n8n.

## Real agents

[Claude Code](claude-code.md) is such an agent: Claude with access to a computer
([Claude, 25:55](https://www.youtube.com/watch?v=mWvtOHlZM-I&t=1555s)). Anthropic starts one with a single loop and the basics a person has at a computer: files, web search,
running code, a to-do list. Tools are removed as needed ([Claude, 25:55](https://www.youtube.com/watch?v=mWvtOHlZM-I&t=1555s), [43:10](https://www.youtube.com/watch?v=mWvtOHlZM-I&t=2590s)).

A better model uses the same tools better, so the agent improves with each new model
without being rebuilt ([Claude, 26:53](https://www.youtube.com/watch?v=mWvtOHlZM-I&t=1613s)).

REA gives an agent tools to examine a program without its source code ([morluto, One MCP for reverse engineering across binaries](https://github.com/morluto/rea#:~:text=One%20MCP%20for%20reverse%20engineering%20across%20binaries), applications, and runtime behavior).

## What can go wrong

**Careful:** each round sends the whole conversation to the model again, and you pay for it each time ([Matt Pocock, Input tokens](https://github.com/mattpocock/dictionary-of-ai-coding#:~:text=Input%20tokens)). A step limit keeps the loop from running forever ([Matt Pocock, 0:00](https://www.youtube.com/watch?v=VxDNUKw83PY&t=0s)).

An agent that reads outside content can be tricked by instructions hidden in it: Prompt injection ([Fireship, 1:53](https://www.youtube.com/watch?v=5uSboan45Zg&t=113s)).

## Where to go next

**Pick the approach**

- An agent decides when to stop; a fixed chain of steps does not: Agent or workflow? ([Matt Pocock, 3:57](https://www.youtube.com/watch?v=AtYtuVTZCQU&t=237s)).
- Act or recall: RAG ([IBM Technology, 1:59](https://www.youtube.com/watch?v=7HSSR1n8dgc&t=119s)).

**Run one**

- Docker's tool for describing an agent in a YAML file and running it: Docker Agent ([Better Stack, 0:46](https://www.youtube.com/watch?v=Mph1H5u3yeA&t=46s)).
- Anthropic's hosted place to run one: Claude Managed Agents ([KodeKloud, 0:00](https://www.youtube.com/watch?v=hbRQqEcvBeI&t=0s)).
- A coding agent run on a fresh start each round: Ralph loop ([AI Engineer, 27:10](https://www.youtube.com/watch?v=c35YoMdnI78&t=1630s)).

**Keep it safe**

- Where agents go wrong: Why agents fail ([IBM Technology, 12:11](https://www.youtube.com/watch?v=D37Ijn2o5U0&t=731s)).
- A rules layer that checks their actions: Ontology guardrails ([AI Engineer, 17:24](https://www.youtube.com/watch?v=Sir59K8ZDPU&t=1044s)).

**Split the work and test it**

- See also Subagents.
- To gain confidence an agent does its job before you ship it, use [Evals](evals.md) ([AI Engineer, 2:07](https://www.youtube.com/watch?v=FB-MLPhL9Ms&t=127s)).
- Checking the code agents write: Guide, verify, solve ([AI Engineer](https://www.youtube.com/watch?v=VrpEyglYgeU)).

## Sources

- [Tool, skill, or subagent? Decomposing an agent that outgrew its prompt](https://www.youtube.com/watch?v=mWvtOHlZM-I), Claude, 2026-05-23
- [You NEED to Use n8n RIGHT NOW!! (Free, Local, Private)](https://www.youtube.com/watch?v=ONgECvZNI3o), NetworkChuck, 2025-07-16
- [7 AI Terms You Need to Know: Agents, RAG, ASI & More](https://www.youtube.com/watch?v=VSFuqMh4hus), IBM Technology, 2025-09-01
- [AI Coding Dictionary](https://github.com/mattpocock/dictionary-of-ai-coding), Matt Pocock, 2026-09-24
- [AI Agents are SO simple to build](https://www.youtube.com/watch?v=VxDNUKw83PY), Matt Pocock, 2025-09-24
- [REA: Reverse Engineer Anything](https://github.com/morluto/rea), morluto, 2026-10-25
- [OpenAI’s new browser feels familiar…](https://www.youtube.com/watch?v=5uSboan45Zg), Fireship, 2025-10-22
- [Most devs don't understand what agents are](https://www.youtube.com/watch?v=AtYtuVTZCQU), Matt Pocock, 2025-10-08
- [ADK vs RAG: How to Choose the Right AI Stack](https://www.youtube.com/watch?v=7HSSR1n8dgc), IBM Technology, 2026-04-21
- [Why I’m Switching From Python to Docker Agent for AI Agents](https://www.youtube.com/watch?v=Mph1H5u3yeA), Better Stack, 2026-10-10
- [What is Claude Managed Agents?](https://www.youtube.com/watch?v=hbRQqEcvBeI), KodeKloud, 2026-05-11
- [The Great Loops Debate — Dex Horthy, Geoff Huntley, Ian Livingstone, Greg Pstrucha, @insecure-agents](https://www.youtube.com/watch?v=c35YoMdnI78), AI Engineer, 2026-07-17
- [Why Agentic AI Fails: Infinite Loops, Planning Errors, and More](https://www.youtube.com/watch?v=D37Ijn2o5U0), IBM Technology, 2026-05-14
- [Why Agentic Systems Need Ontologies — Frank Coyle, UC Berkeley](https://www.youtube.com/watch?v=Sir59K8ZDPU), AI Engineer, 2026-07-23
- [The maturity phases of running evals — Phil Hetzel, Braintrust](https://www.youtube.com/watch?v=FB-MLPhL9Ms), AI Engineer, 2026-05-27
- [In the Land of AI Agents, the Verifiers Are King — Tariq Shaukat, Sonar](https://www.youtube.com/watch?v=VrpEyglYgeU), AI Engineer, 2026-07-20
