---
type: source
platform: youtube
date_found: 2026-02-28
relevance: critical
topic: openclaw-obsidian-integration
author: Dave
tags: [source, openclaw, obsidian, memory, qmd, integration, setup-guide]
---

# OpenClaw + Obsidian — "Persistent Memory That Actually Works"

*Dave's video: integrating OpenClaw agent "Lloyd" with Obsidian vault on Mac Mini*

## The Problem He Solved
> "The promise of persistent forever memory is kind of a lie. It doesn't work, at least out of the box."

OpenClaw's built-in memory (MEMORY.md) isn't enough. He uses Obsidian as an external, structured, searchable knowledge base that the agent indexes.

## His Setup
- **Hardware:** M1 Mac Mini under the stairs (always-on)
- **Agent:** "Lloyd" running OpenClaw
- **Access:** iMessage (Apple ID for the agent), wife also has access
- **Sync:** Network drive synced across machines (or Obsidian Sync at $5/mo)
- **Remote access:** Tailscale for accessing from anywhere

## Step-by-Step Process

### 1. Create Vault
- Download Obsidian (free)
- Create vault (= folder of markdown files)
- **⚠️ No spaces in vault name!** Agent couldn't index with spaces. Used "Daves-vault" instead.

### 2. AI-Generated File Structure
- Showed agent the reference article (Heinrich's X article about Claude Code + Obsidian)
- Told agent to adapt template for his needs
- Agent asked clarifying questions about family, goals, use cases
- Agent built entire folder structure automatically
- Agent also created guide files (e.g., `inbox-guide.md`) teaching itself how to handle each folder

### 3. Migrate Existing Notes
- Dropped sample notes in vault root
- Told agent: "take the sample notes and put them in the best fitting folders"
- Agent organized everything automatically

### 4. Connect Vault to OpenClaw (QMD Indexing)
- Edit `openclaw.json` config file
- Find `memory` block → replace with new config pointing to vault path
- Config snippet includes vault path for QMD (semantic search) indexing
- **Get path:** Right-click folder → Option+Copy → "Copy as Pathname"
- Restart agent → QMD indexes all notes
- Can also tell agent to edit config for you (agents fixing agents!)

### 5. Test & Use
- "Search my vault for notes about deep work" → found 6 interconnected notes
- "Create a note about my plans to become an astronaut" → created full plan in Projects folder
- "What patterns exist in my thinking notes?" → analysis of thinking patterns across vault

## Key Insights

### Agent Builds Its Own Structure
The agent doesn't just use the vault — it **creates the organizational system**. When given the reference article, it proactively:
- Built folder hierarchy tailored to user's actual life
- Created guide files teaching itself vault conventions
- Asked clarifying questions before building
- Organized existing notes into correct folders

### QMD Semantic Indexing
- OpenClaw indexes the entire vault for semantic search
- Agent can find notes by meaning, not just keywords
- WikiLinks between notes are preserved and understood
- **⚠️ No spaces in vault name** or indexing fails

### Security Considerations
> "If anyone ever breached the agent's trust, your notes would become accessible. And this info will be shared with whatever LLM provider you're using."

- Local LLM = no cloud exposure
- Cloud LLM (OpenAI, Anthropic) = your thoughts go to the cloud
- Consider what goes in the vault carefully

### Sync Options
| Method | Cost | Complexity |
|--------|------|-----------|
| Obsidian Sync | $5/mo | Zero (built-in) |
| Network drive | Free | Medium (NAS/shared folder) |
| Tailscale + local | Free | Medium (VPN setup) |
| iCloud/OneDrive | Free | Low (but potential conflicts) |

## 💡 Takeaways for DECA

### Directly Applicable RIGHT NOW
1. **QMD indexing** — Our OpenClaw can index an Obsidian vault for semantic search. Need to configure `openclaw.json` memory block to point to vault.
2. **Agent builds the structure** — Instead of us designing everything manually, tell Klawdiy to build the vault structure based on DECA's needs + the research we've collected.
3. **No spaces in vault names** — Important technical gotcha.
4. **Guide files per folder** — Agent creates `guide.md` in each folder teaching itself conventions. Self-documenting system.

### Architecture Validation
5. **Network sync works** — Dave uses network drive to sync between machines. We can use GitHub (already set up) or rclone to Google Drive.
6. **Wife access pattern** — Multiple people can use the same vault. Vlad + agents all access same knowledge base.
7. **"Agents fixing agents"** — If config breaks, use another agent to fix it. We already do this.

### What We Should Do
- [ ] Configure OpenClaw's `openclaw.json` to point memory/QMD at our vault
- [ ] Test semantic search: "find all customers worried about price"
- [ ] Add guide.md files to each folder explaining conventions to agents
- [ ] Consider Tailscale for Vlad's mobile access to VPS vault
