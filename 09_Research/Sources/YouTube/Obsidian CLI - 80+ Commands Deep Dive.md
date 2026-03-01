---
type: source
platform: youtube
date_found: 2026-02-28
relevance: critical
topic: obsidian-cli
tags: [source, plugin, obsidian-cli, ai-integration, claude-code, openclaw]
---

# Obsidian CLI — 80+ Commands (Full Video Breakdown)

*Video transcript processed from NotebookLM. Author demonstrates every CLI category with Claude Code.*

## What Is Obsidian CLI
- Official CLI shipped with **Obsidian 1.12** (Catalyst license required)
- 80+ terminal commands to control Obsidian programmatically
- Replaces the mess of MCP servers, REST API plugins, Obsidian URI
- **CLI > MCP** because: faster, direct file access, no auth needed, more context efficient
- **Progressive disclosure**: agent runs `obsidian help` → discovers available commands on its own (doesn't need all tools loaded in memory)

## Why CLI > MCP
| CLI | MCP |
|-----|-----|
| Faster | Slower |
| Direct local file access | Requires server setup |
| No authentication | Auth required |
| Context efficient | More overhead |
| Piping actions together | Individual calls |
| Agent self-discovers via `help` | Must pre-load all tools |

## Command Categories (80+)

### 1. Daily Notes as Universal Inbox
- `obsidian prepend` — add content to daily note from CLI
- Works via Telegram: voice note → agent → appends to daily note → shows as task
- **Demo:** "append brilliant idea to daily note" → Claude runs `obsidian prepend` → appears in Obsidian instantly
- Unified inbox: Telegram, terminal, agent — all write to same daily note
- **💡 DECA:** Vlad voice notes via Telegram → Klawdiy appends to vault daily note. Zero friction capture.

### 2. Task Management (without opening files)
- List unchecked tasks: `obsidian tasks` (in daily note)
- Mark tasks done from CLI
- List tasks by tag: `#quick`, `#deep`, `#evening`
- Scale up: Telegram bot → ask about current tasks → mark done
- **💡 DECA:** "What deals need follow-up today?" → agent queries tasks from vault → returns list via Telegram

### 3. File Operations (backlink-safe!)
- **Critical:** Normal `mv` command BREAKS backlinks in Obsidian!
- CLI `rename` and `move` commands preserve all backlinks
- Demo: renamed file → "updated 14 links" automatically
- Create files, open files, open in sidebar/new pane
- **💡 DECA:** When deal moves from "Negotiating" to "Won" → agent uses CLI move (not filesystem mv) → all backlinks preserved

### 4. Vault Health Analysis
- `obsidian` commands to find:
  - **Dead ends** — files with no outgoing links
  - **Orphans** — files with no incoming links
  - **Broken links** — references to non-existent files
  - **Backlinks** — what points to a specific file
- Can generate full health report with suggestions
- **💡 DECA:** Daily cron: "analyze vault health" → find customers with no recent interactions, deals with broken links, orphan files. Auto-report.

### 5. Properties (YAML frontmatter) — WITHOUT reading files!
- `obsidian set-property status done` — changes frontmatter without reading file content
- **This is huge for token efficiency**: previously agent had to read entire file just to change one property
- Demo: changed status of multiple files from "unread" to "processed" without reading any
- Limitation: somewhat slow for bulk operations
- **💡 DECA:** Update deal stage, customer status, last_contact date — all without reading the full customer file. Massive token savings.

### 6. Search & Tags
- Search by tags across vault
- List files with specific tags
- Can combine with Dataview for complex queries
- Initial setup may need guidance, but once working → add to memory for reuse
- **💡 DECA:** "Find all #hot customers assigned to #eric" → instant results

### 7. Bases Querying (Obsidian Bases as Database)
- Query any `.base` file from CLI
- Returns structured data (frontmatter only, not full file content!)
- **Key insight:** "We only read frontmatter, saving so many tokens. What I see in Obsidian is exactly what Claude sees — we're on the same page"
- Can query: bookmarks, skills, journals, meetings, clients, projects
- **💡 DECA:** Query customer base: "show all active deals over $50K" → agent reads only frontmatter → aligned with what Vlad sees in Obsidian

### 8. Bookmarking from Agent
- Agent can bookmark URLs, YouTube videos, articles into Obsidian Base
- Send picture to Telegram bot → gets filed into proper folder
- Uses custom bookmark skill

### 9. Version History
- `obsidian history` — shows all saved versions of a file
- Can go back to any version
- Can analyze evolution: "what changed from version 15 to current?"
- Agent compares versions and summarizes changes
- **💡 DECA:** Track how a quote evolved, what changed in customer notes over time

## Key Quotes
> "CLI is a bridge between AI agent and your vault"
> "We only read the frontmatter — we don't have to read complete files, which is such a waste"
> "You and the agent are aligned — what you see in Obsidian is exactly what the agent sees"
> "Everything I showed is building blocks — connect them and you get your personal operating system"

## Technical Requirements
- **Obsidian 1.12+** with Catalyst license
- Enable CLI in Obsidian settings
- Works with: Claude Code, OpenClaw, any CLI-based agent

## 💡 Top Takeaways for DECA

### Must-Have
1. **Properties without reading files** — update deal stages, customer status for 195 contacts without burning tokens
2. **Bases querying** — structured queries on frontmatter = our Command Center but in Obsidian
3. **Backlink-safe file operations** — moving deals between stages preserves all connections
4. **Vault health audits** — automated orphan/dead-end/broken-link detection

### Should-Have
5. **Daily note as inbox** — Vlad voice → Telegram → vault daily note
6. **Task management from CLI** — "what needs attention today?" without opening Obsidian
7. **Version history** — track quote evolution, customer file changes

### Nice-to-Have
8. **Bookmarking from agent** — auto-file research links into vault
9. **Progressive disclosure** — agent discovers commands as needed, not pre-loaded
