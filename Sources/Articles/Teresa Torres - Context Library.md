---
type: source
platform: podcast/blog
url: "https://www.chatprd.ai/how-i-ai/teresa-torres-claude-code-obsdian-task-management"
date_found: 2026-02-28
date_published: 2026-01-19
relevance: critical
tags: [source, ai-integration, architecture, context-management]
---

# Teresa Torres — "Lazy Prompting" with Granular Context Library

## Why Relevant
Product management expert who built an entire task management + research system in Obsidian powered by Claude Code. Solved the **context overload problem** that we face.

## The Problem She Solved
When AI loaded all her context, it pulled marketing strategy when she asked about her dog. **Too much irrelevant context is as bad as too little.**

Solution: Break context into **dozens of tiny, focused markdown files** in an Obsidian vault called "LLM Context."

## Her System

### /today Slash Command
Every morning runs a Python script that:
- Scans all task files
- Assembles daily to-do list
- Shows overdue tasks
- Links to research digest

### Tasks as Markdown Files
Each task = its own `.md` file with YAML frontmatter:
```yaml
type: task
due_date: 2024-08-21
tags:
  - sales
  - course-launch
```

### Natural Language Task Management
Just types: "new task, send thank you to Claire, do today"
→ Claude creates markdown file, adds YAML, updates daily list

### Automated Research Digest
- Cron job searches arXiv daily for her topics
- Summarizes new papers overnight
- Results appear in daily to-do list

## 💡 Takeaways for DECA
- **Granular files > monolithic blobs** — agent reads only what it needs
- **YAML frontmatter is the key** — structured, queryable, AI-parseable
- **"LLM Context" vault concept** — separate context layer specifically for agents
- **Daily digest pattern** — could be our morning sales briefing, generated FROM vault data
- **Natural language file creation** — "new customer David Jones, $95K deal, Decision Maker stage" → agent creates the file
- This validates that Obsidian vault = the RIGHT approach for AI context management
