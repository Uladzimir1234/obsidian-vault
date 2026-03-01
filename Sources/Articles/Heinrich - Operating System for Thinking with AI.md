---
type: source
platform: blog/x-thread
date_found: 2026-02-28
relevance: critical
topic: vault-philosophy-architecture
author: Heinrich
tags: [source, architecture, philosophy, claude-code, vault-design, critical]
---

# Heinrich — "An Operating System for Thinking with AI"

*The original article that inspired Dave's video and many others. Core philosophy for vault design.*

## Core Thesis
> "You don't take notes anymore. You operate a system that takes notes."
> "Vibe coding changed how we write software. Vibe note-taking changes how we think."

## The Big Insight: Knowledge = Code
Knowledge bases and codebases have a lot in common:
- Both are folders of text files with relationships
- Both have conventions and patterns
- Both benefit from agents that navigate and operate them
- **Every note is basically a skill** — curated knowledge that gets injected when relevant

## Vault Architecture

```
vault/
├── 00_inbox/        # capture zone, zero friction
├── 01_thinking/     # your notes and synthesis
│   ├── notes/       # individual thinking notes
│   └── topic-pages  # MOCs (Maps of Content)
├── 02_reference/    # external knowledge
│   ├── tools/
│   ├── approaches/
│   └── sources/
├── 03_creating/     # content in progress
├── 04_published/    # finished work
├── 05_archive/      # inactive content
├── 06_system/       # templates and scripts
├── CLAUDE.md        # teaches AI the system
└── attachments/
```

## How Agent Finds Things (3 Layers)

### Layer 1: Session Start Hook
```json
"hooks": {
  "SessionStart": [{
    "command": "tree -L 3 -a -I '.git|.obsidian' --noreport"
  }]
}
```
Agent sees folder structure automatically at session start.

### Layer 2: Index File
Lists every note with a one-sentence description. Agent scans 50 notes in seconds without opening them.

### Layer 3: Topic Pages (MOCs)
- Link to related notes like a table of contents
- **Agent leaves notes for itself** about what it learned while traversing the graph
- Future sessions read these breadcrumbs → vault remembers how to think through itself

## Writing Rules

### Links as Thoughts, Not References
❌ "This relates to quality. See: quality-note"
✅ "Because [[quality is the hard part]] we need to focus on curation"

The link becomes part of the thought. Agent follows reasoning by following links.

### Name Notes as Claims, Not Topics
❌ "Thoughts on AI slop"
✅ "Quality is the hard part"

When linking, the title becomes part of your sentence naturally. Forces deeper thinking.

### Composability
> "Can this note be linked from elsewhere and still make sense? If linking to it forces you to explain three other things first, split it up."

Notes = Lego blocks. Each complete on its own, but connect to build bigger structures.

### Network > Individual Notes
> "A note with many incoming links is more valuable than an isolated note. Every link creates a new reading path. The network IS the knowledge."

## Agent Operating Rules

1. **Every task starts with orientation** — scan structure, check index, read topic page BEFORE changes
2. **Follow links to build understanding** — no changes without context
3. **Record navigation discoveries** — when agent learns something useful about a topic, it records in the topic page
4. **Emergence detection** — when two notes interact interestingly, create a new note capturing the combined insight
5. **Auto-linking** — every new capture triggers search for related notes, add links with context

## Philosophy: Every Vault Needs Its Own Rules

> "Most guides get wrong: they give you a system and say follow this. But every vault serves a different purpose."

| Vault Type | Emphasizes |
|-----------|-----------|
| **Work/CRM** | Capture first, structure later. Project folders. Client context. |
| **Research** | Source tracking, citations, claim verification |
| **Creative** | Idea capture, draft progression, reference organization |
| **Thinking** | Depth over breadth, quality over speed, synthesis |

### His Thinking Vault Philosophy
```markdown
Depth over breadth. Quality over speed. Tokens are free.
This is not about efficiency. This is about excellence.
```

## Multiple Vaults Pattern
He runs multiple vaults with different rules:
- Thinking vault = AI + knowledge management philosophy
- Work vault = projects + clients with completely different rules
- Same underlying pattern, different rules per purpose

**The constant pattern:**
1. Markdown files with links
2. CLAUDE.md that teaches agent the system
3. Structure for quick orientation
4. Conventions written as instructions

## Key Quotes
> "A vault encodes HOW you think, not just what you thought about."
> "The methodology becomes part of the system."
> "I realized: I only work in the vault now."
> "Watching an AI completely disrespect my philosophies taught me that you have to textualize everything."
> "My CLAUDE.md is around 2000 lines now because I keep refining."

## 💡 Takeaways for DECA

### Critical Architecture Decisions
1. **Multiple vaults** — We should have separate vaults: CRM vault (customers, deals, products) vs Research vault (this brainstorm). Different rules per purpose.
2. **Index file** — Create an index listing every note with one-sentence description. Agent scans this FIRST, not individual files. This is the answer to our 13MB JSON problem.
3. **Topic pages (MOCs)** — "Customers by Eric", "Deals in Negotiating", "S8000 IQ Projects" — these are navigational hubs.
4. **Agent breadcrumbs** — Agent records what it learned while navigating. Future sessions benefit. Self-improving vault.

### Writing Conventions for DECA Vault
5. **Notes as claims** — Not "David Jones info" but "David Jones needs $95K Revival Homes project by Q2"
6. **Links in sentences** — "[[David Jones]] is working with [[Eric Yurtuc]] on a [[LINEAR]] project" — agent follows reasoning
7. **Composability** — Each customer file must stand alone. No "see also" chains.

### Agent Operations
8. **Orientation first** — Agent scans structure → reads index → reads topic page → THEN acts
9. **CLAUDE.md / SOUL.md** — Our vault needs its own philosophy document. Work vault = "capture first, client context, action-oriented"
10. **Emergence detection** — When agent notices two customers have similar objections → create a pattern note

### The Deepest Insight
> "You're not taking notes anymore but directing a system that takes notes. Your job becomes judgment — deciding what matters."

This is EXACTLY what Vlad should be doing. Not writing customer notes. Directing a system (Klawdiy + vault) that captures everything, and judging what matters.
