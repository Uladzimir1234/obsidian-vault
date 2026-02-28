---
type: source
platform: notebooklm
date_found: 2026-02-28
relevance: critical
format: csv-export
tags: [source, pattern, workflow, ai-integration, notebooklm]
---

# Workflows & Patterns — NotebookLM Research Export

*9 workflow patterns extracted from NotebookLM research across multiple sources*

## 1. Meeting Synchronization
- **What:** Auto-sync meeting transcripts into Obsidian → create tasks and summaries
- **Tools:** Granola, Claude Code, Obsidian
- **How:** Custom 'Granola skill' for Claude Code accesses meeting audio/text → appends to Markdown files
- **💡 DECA:** We could auto-sync Quo call summaries into customer vault files. Already have the data — just need the output format.

## 2. Multi-Source Research Analysis
- **What:** Analyze 20+ sources (YouTube, PDFs, articles) simultaneously for gaps and trends
- **Tools:** NotebookLM, Gemini, Claude Code, Obsidian
- **How:** Claude Code CLI skill programmatically uploads sources to NotebookLM → exports cited results to Obsidian
- **Key benefit:** Grounded citations solve hallucination — answers tied to actual source passages
- **💡 DECA:** Load all Gealan PDFs + competitor sites + sales transcripts into NotebookLM → get grounded product answers. This is huge for quote generation accuracy.

## 3. Obsidian Base Querying
- **What:** Claude queries YAML frontmatter as a database (like Notion) without reading full file content
- **Tools:** Obsidian Base Plugin, Claude Code, Vault Query Plugin
- **How:** Script parses frontmatter into JSON → Claude filters and queries
- **Key benefit:** Efficient planning without reading every file
- **💡 DECA:** THIS IS THE KEY PATTERN. Agent queries `type: customer, status: active, seller: Eric` → gets list without loading 195 customer files. Solves our 13MB JSON problem.

## 4. Mobile Semantic Search
- **What:** Natural language search on knowledge base from mobile
- **Tools:** Claude Code, Termius, Tailscale, QMD (Semantic Search Engine)
- **How:** SSH into local machine via Tailscale → run CLI search commands via Termius
- **Key benefit:** Find info by meaning, not just keywords ("customers worried about price")
- **💡 DECA:** Vlad could search "who hasn't been contacted in 2 weeks" from his phone. Need to evaluate QMD.

## 5. Context Persistence (Dashboard Pattern)
- **What:** Project-specific dashboards storing session history + decisions
- **Tools:** Claude Code, Obsidian, Custom Skills
- **How:** Save session logs as Markdown → instruct AI to read 'last session' file on start
- **Key benefit:** No re-explaining context. Minimizes token usage.
- **💡 DECA:** We already do this with MEMORY.md! But per-project dashboards (per-customer?) could be next level. Agent opens David Jones dashboard → knows everything instantly.

## 6. Obsidian CLI Control (80+ commands)
- **What:** Manipulate Obsidian programmatically from terminal
- **Tools:** Obsidian CLI (Catalyst version), Claude Code, OpenClaw
- **How:** Install Catalyst version of Obsidian, enable CLI in settings
- **Commands:** Health checks (broken links), property updates, file operations — all without UI
- **💡 DECA:** Vault health audits! Auto-detect: orphan customers, broken links, stale deals, missing properties. Run daily via cron.

## 7. Automated Morning Briefing
- **What:** 24/7 assistant aggregates tasks, calendar, health metrics → daily report
- **Tools:** Clawdbot (Telegram), Cron Jobs, Obsidian, Python Scripts
- **How:** Mac Mini runs cron at 7AM → Claude compiles data into PDF → sends via Telegram
- **💡 DECA:** We already have this! Our 8AM/6PM briefings via Telegram. But generating from VAULT data instead of raw API calls = faster, cheaper, more structured.

## 8. Audio Overviews / Podcasts
- **What:** Generate audio deep-dives from research sources or personal notes
- **Tools:** NotebookLM, Claude Code, Obsidian Sync
- **How:** Trigger NotebookLM 'Audio Overview' → sync MP3 to mobile
- **💡 DECA:** Weekly sales podcast for Vlad? "Here's what happened this week, top deals, issues, opportunities" — listen while driving. NotebookLM generates it from vault data.

## 9. Feedback Loop Analysis (Self-Improving AI)
- **What:** Analyze past AI conversations → auto-improve system instructions
- **Tools:** Claude Code, Session Analysis Skill, Whisperflow
- **How:** Claude parses its own session JSON cache → proposes updates to memory file
- **Key benefit:** Self-improving assistant that learns from its mistakes
- **💡 DECA:** We should do this! Klawdiy reviews own sessions → updates SOUL.md, MEMORY.md, agent rules. "Last time I misclassified a lead because X → update classification rules."

---

## Priority Matrix for DECA Implementation

| # | Pattern | Already Have? | Priority | Effort |
|---|---------|:---:|:---:|:---:|
| 3 | Base Querying (YAML as DB) | ❌ | 🔴 HIGH | Medium |
| 5 | Context Persistence Dashboard | ✅ Partial | 🔴 HIGH | Low |
| 7 | Morning Briefing from Vault | ✅ Yes (API) | 🟡 MEDIUM | Medium |
| 2 | Multi-Source Research | ❌ | 🟡 MEDIUM | High |
| 9 | Feedback Loop / Self-Improving | ❌ | 🟡 MEDIUM | Medium |
| 6 | Obsidian CLI Health Audits | ❌ | 🟡 MEDIUM | Low |
| 1 | Call Sync to Vault | ✅ Partial | 🟢 LOW | Low |
| 4 | Mobile Semantic Search | ❌ | 🟢 LOW | High |
| 8 | Audio Podcasts | ❌ | 🟢 LOW | Low |
