# utd-journal-writing

A [Claude Code](https://claude.com/claude-code) skill for writing and revising academic prose in the style of top operations and management journals — *Management Science*, *M&SOM*, and *Production and Operations Management* (the UTD-24 journals) — using [University of North Carolina Writing Center](https://writingcenter.unc.edu/tips-and-tools/) principles for flow, conciseness, paragraphs, and transitions.

## What it does

The skill produces and repairs journal-style prose. It works on any chunk of text — a sentence, a paragraph, or a whole section — in two modes:

- **Revise** — paste a rough draft; it rewrites into clean UTD-journal prose and tells you the key moves it made.
- **Draft** — give it notes or an outline; it builds claim-first paragraphs that argue rather than report.

It covers sentence- and paragraph-level mechanics (old-to-new flow, conciseness, transitions, paragraph unity, intuition paragraphs) and, for introductions, the six-move structural template these journals follow.

## What's inside

```
utd-journal-writing/
├── SKILL.md                    # the skill: voice, flow, paragraphs, conciseness, anti-patterns
└── references/
    └── introduction.md         # the six-move introduction template + craft moves
```

`SKILL.md` governs the sentences; `references/introduction.md` loads when you're working on an introduction and governs the structure.

## Principles it encodes

- **Old-to-new flow** as the highest-leverage cohesion device — open each sentence on known information, end on the new.
- **Claim-first paragraphs** — topic sentences that make an arguable claim, developed as claim → support → why → link.
- **Surgical hedging** — assert what's proven or precisely estimated; qualify only the genuine causal or practical reach.
- **Conciseness** — cut wordy openers, expletive constructions, nominalizations, and empty qualifiers.
- **Calibrated self-claims** — keep evaluative adjectives out of results narration; confine contribution-framing to the contribution paragraph.
- **Introduction architecture** — phenomenon → puzzle → earned research questions → model preview → directional findings preview → novelty quarantined to the literature.

The guidance is calibrated against real prose from published and forthcoming papers in these journals, not a generic "make it formal" prior.

## Install

Drop the folder into your Claude Code skills directory:

```
~/.claude/skills/utd-journal-writing/
```

Claude Code will pick it up automatically. Invoke it by asking to write, revise, tighten, or "make this read like Management Science" for any part of an operations/management paper.
