# Writing

How a note, a path and a topic are written here. Read it before you add or change one.

## A note

A note answers one question, in one of three kinds: an explainer ("what is X?", one thing), a guide ("how do I do
Y?", in steps) or a comparison ("X or Y, and when?", ending with which to pick when).

```yaml
---
title: "Claude Code"
type: explainer           # explainer, guide or comparison
line: "…"                 # what it is or what you get, 30 words at most
topic: "Claude Code"      # its topic in topics.md
tags: [agent, terminal]
aliases: ["claude"]       # other names a reader searches for; never used twice across notes
related: [skills]         # slugs of other notes
updated: 2026-10-23
---
```

Then `# Title`, the line again in italics, and the body.

- Write for the non-technical reader first: short sentences, one idea each. Explain or link a word the first time
  the body uses it, including the words a newcomer guesses at: "hosted", "endpoint".
- Every sentence gives the reader something they need. Past about 300 words for an explainer (390 for a guide or a
  comparison, citations not counted), look for what repeats, wanders or is a second idea (two notes).
- The point first: the first sentence says what it is or what you get. A reader who stops there still knows.
- A title is the thing's name, as short as a reader says it: "Red, green, refactor".
- Say what a thing is. No contrast after a comma ("summoned, not raised") in a title, a line or a heading.
- No people's names: the source carries its author. Say who by role ("an n8n teacher", "Anthropic's engineer").
  A company may be named when it matters whose claim it is. A creator is "they".
- An explainer says what it is not, when readers are likely to mix it up with something else.
- One home per fact: a guide links an explainer, never restates it.
- `## My take` (or `## My recipe …`, the owner's own recipe): the owner's own view, written by the owner alone. Once, the last section before What changed.

## Citing

- Every claim cites its source at the spot, in brackets after it:
  - a video at a time: `([A creator, 12:30](https://www.youtube.com/watch?v=ID&t=750s))`
  - a page at a heading: `([A site, Pricing](https://example.com/page#:~:text=Pricing))`
  - the text under a video, or a page as a whole: `([A creator](https://www.youtube.com/watch?v=ID))`
- A citation backs what comes before it in its paragraph or list item, back to the citation before.
- Every cited source goes in the note's `## Sources`, its last section: `- [Its title](link), its author, its date`.
- What a source claims is the source's claim: "Anthropic says", "one test found". Never stated as fact when only one
  creator says it. "Two creators say" only when both say it, both cited.
- Sources disagree, and both may still hold: the note keeps both, each cited, and says which holds up better and
  why, by the claim's kind ("Which claim holds up"). Nothing to tell them apart: the note says the question is open.
- Your own arithmetic on a source's number is not the source's claim: leave it out, or cite the number.
- A safety warning (a secret, data loss, a bill, who gets access) is a line of its own: `**Careful:** …`, one or two
  sentences. Cite a source that says it. None does? It stands uncited.

## Which claim holds up

A claim's kind sets its test. The date alone never decides (the user, 2026-11-02).

- News (an event, a release, a price on a day): real when the maker's own word, two independent sources or figures
  back it. One creator alone: "one creator reports". Hype with nothing behind it stays out. A dated event stays true.
- A fact that changes (what a tool does now, a price now): the newer source wins.
- A definition: a product's term follows its maker. A general term follows the field's use now. Two contexts: both,
  each named by its context. One context: the knowledge base's own notes win. A source that calls a skill an agent
  is wrong on that point.
- An interpretation (why something matters): a source's view, "X says". Its date counts for nothing. What stands
  behind it counts.
- A lasting idea (how something works) and a general lesson (what to do): their date counts for nothing. A lesson is
  general only with a study, data, or two independent creators. Else: "one creator found".
- The owner's own lesson (`## My take`, `## My recipe …`): never changed by a writer or a check. A source against it
  goes to the owner, who decides.

Weigh by evidence:

- A test or data over an opinion. A maker's own word over a reseller's. A person in their own field over one outside
  it. Fame adds nothing.
- An idea that held for decades weighs more. Stronger evidence still beats it. One new finding against it: both stay,
  and the question is open until an independent source confirms the finding.
- One person is one voice, however many videos or clips. A guest on a channel is their own voice, not the channel's.
  The same view across their sources weighs more. A flip with no reason weighs less. A change with a reason ("I tried
  it, it was wrong") is their view now, however big. A detail refined is no flip.

## When it changes

- When what a note says stops being true, the note says the new thing and logs the change in `## What changed`,
  newest first, one entry per change: `- 2026-09-22 · big: what changed.` then `Was: … Now: … (cited).`
  Its day is the day the knowledge changed, not the day the note was written. Small: a detail moved. Big: the advice
  changed.
- A release (a model's version) is an explainer with `released: 2026-09-22`, `family: <the family's note>` and
  `supersedes: <the release before it>`. A new release goes in its family's note too.

## Links

- To a note: `[Title](slug.md)`, or `[a label](slug.md#a-heading)`. From `topics.md` or `paths.md`: `notes/slug.md`.
- Out of the knowledge base: `[a label](https://…)`.

## A path

`paths.md` holds the reading paths, in the order a newcomer reads them: `## Its name`, one line on what the reader
gets, then its notes as `1. [Title](notes/slug.md)`, in reading order.

- Each note needs only the ones before it, on its path or an earlier one. 2 to 8 notes a path.
- A note is on one path at most, a release never: its family stands for it.

## A topic

`topics.md` is the tree: `## A topic`, then its notes as `- [Title](notes/slug.md): its line`; or, for a big topic,
`### A group`s with theirs. Two layers at most.

- A new note goes in it in the same change, under the topic and group where a reader looks for it.
- Every note once, a release never.
- "Open models", never "open-source": most share their weights, not how they were made.
