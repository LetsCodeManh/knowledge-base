# Knowledge base: for an agent

Notes on AI and the tools around it, written for a non-technical reader. Each claim links its source at the spot.
Licence: CC BY-NC 4.0 (`LICENSE`), non-commercial use only. Credit "Manh Ng" and link this repo.

## Find a note

- `topics.md`: every note by topic, with its one-line summary. Start here.
- `paths.md`: reading paths for a newcomer, in order.
- `notes/<slug>.md`: one note. Its frontmatter holds `title`, `line` (the summary), `aliases` (other names) and `related`.
- Search the titles, the aliases and the bodies. A note links another as `[Title](slug.md)`.

## Answer from the notes

- Say only what a note says. Do not add to it from memory.
- Link the note you answer from. Give the source link next to a claim when the reader wants to check it.
- A claim in a note is its source's claim ("one test found"). Keep it so.
- A `**Careful:**` line is a safety warning. Keep it in your answer.
- `## What changed` lists what stopped being true, newest first. Read `updated`: a fast topic goes stale.
- The notes do not answer it? Say so. The `research` skill finds the rest.

## Add or change a note

- Search first: `topics.md`, then the titles and `aliases`. A note covers it? Change that note.
- Follow `writing.md`. Use public sources only, each with a link.
- Check before you hand back:
  - Each claim has a citation to a spot the source has.
  - Each cited source is in the note's `## Sources`.
  - Each `[Title](slug.md)` link opens a note that is here.
  - The first sentence says what it is or what you get.
- Send it as a pull request. The owner checks each citation against its source before it goes in.

## Skills

- `.claude/skills/research/SKILL.md`: researches a question. The notes first, then the web for what they lack.

Claude Code loads it. Another agent: read the file and follow it.
