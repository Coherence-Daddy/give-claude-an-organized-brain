# Give Claude an Organized Brain

> **Coherent Obsidian Skills · Episode 01**
> Folders organize bytes. Frontmatter organizes meaning.

A 5-minute walkthrough that grafts two upstream patterns onto your Obsidian
setup so Claude can reason about your notes as a typed knowledge graph:

1. **The `obsidian-power-user` skill** from [Sleestk/Skills-Pipeline](https://github.com/Sleestk/Skills-Pipeline) — drops into your `.claude/skills/` so Claude has full Obsidian fluency (Templates, Bases, Dataview, Canvas, plugin lore, the works).
2. **Kepano's wikilinks-in-YAML frontmatter** convention from [kepano/kepano-obsidian](https://github.com/kepano/kepano-obsidian) — every note declares `categories: [[Project]]`, turning the vault into a parseable graph readable by Obsidian's graph view, Bases queries, Dataview, *and* any indexer (e.g. local-brain → Qdrant).

## Watch the tutorial

→ **[coherencedaddy.com/tutorials/give-claude-an-organized-brain](https://coherencedaddy.com/tutorials/give-claude-an-organized-brain)** — 11 slides, ~5 min read.

## Hand it off to Claude

The companion copy-paste setup prompt (in [`prompts/copy-paste-prompt.md`](prompts/copy-paste-prompt.md)) does ~95% of the install end-to-end:

- Clones `Skills-Pipeline` to `/tmp` and copies `Obsidian/obsidian-power-user/` into your `.claude/skills/`.
- Stages the kepano-style scaffolding kit (templates, category index stubs, conventions doc) and drops it into your Obsidian vault root.
- Wires `.obsidian/templates.json` so the Templates core plugin uses the new folder.
- Backfills `categories: ["[[Project]]"]` on every existing `Projects/<slug>/README.md` and `infrastructure.md`.
- (If [local-brain](https://github.com/Coherence-Daddy/use-ollama-to-enhance-claude) is wired) re-indexes both vaults so typed queries work.

Drop the prompt into Claude Code. It walks you through detection → install → backfill → verify with a checklist that updates after every step.

## What's in this repo

```
.
├── index.html                       ← The 11-slide presentation (self-contained, no build step)
├── cd-face-coral.png                ← Brand monogram referenced by the sidebar
├── prompts/
│   └── copy-paste-prompt.md         ← The companion operator prompt — paste into Claude
└── README.md                        ← This file
```

## The two laws (in 30 seconds)

```yaml
---
categories: ["[[Project]]"]                # Law 1: every note has categories
topics: ["[[Knowledge graphs]]", "[[PKM]]"]  # Law 2: typed relations are wikilinks, not strings
author: ["[[Steph Ango]]"]
---
```

That's the entire commitment. Two fields. Wikilinks-not-strings means every
relation becomes a real edge in Obsidian's graph view *and* a parseable field
for any indexer downstream.

## Backfill on touch

Don't do a mass migration — they always give up halfway. Add `categories:` to
a note next time you open it. Two weeks in, your graph fills itself. The
high-leverage one-time pass is just project notes (`Projects/<slug>/README.md` +
`infrastructure.md`); everything else compounds organically.

## License

MIT — copy, fork, remix. Adopt the conventions in your own vault, your own
team's vault, your own product.

## More from Coherence Daddy

- **[Use Ollama to Enhance Claude](https://github.com/Coherence-Daddy/use-ollama-to-enhance-claude)** — pair Anthropic Claude Desktop with Claude Code routed through Ollama. Cuts your Claude Code spend ~90%.
- **[Give Obsidian a Memory](https://github.com/Coherence-Daddy/give-obsidian-a-memory)** — wire Claude Desktop into an Obsidian vault via MCP, with Ollama embedding locally. One-click installer.
- **[More tutorials →](https://coherencedaddy.com/tutorials)**

---

🟠 [coherencedaddy.com](https://coherencedaddy.com)
