---
type: architecture
tags: [plugin, architecture]
---

# Plugins to Evaluate

## Essential (everyone uses these)
| Plugin | What It Does | Status |
|--------|-------------|--------|
| **Dataview** | Query vault as database, tables, lists, task queries | ⭐ Most popular plugin. All CRM implementations use it |
| **Templater** | Dynamic templates with variables, dates, logic | ⭐ Needed for entity creation |
| **Obsidian Bases** | Built-in structured views (table, kanban, calendar) | 🆕 Core plugin since 2025, may replace Dataview for some uses |

## Likely Needed
| Plugin | What It Does | Status |
|--------|-------------|--------|
| **Kanban** | Kanban board view | 🤔 Or use Bases kanban? Need to compare |
| **Calendar** | Calendar view of daily notes | 🤔 Useful for interaction timeline |
| **Excalidraw** | Visual diagrams, whiteboarding | 📝 Mentioned as "amazing" by Tech Sales guy |

## For AI Integration
| Plugin | What It Does | Status |
|--------|-------------|--------|
| **Agent Skills** (kepano) | Teaches agents Obsidian conventions | ⭐ Official, by CEO. Install this. |
| **Terminal** | Terminal window inside Obsidian | 🤔 For local Claude Code use (not our case) |
| **Agent Client** | Claude Code / Codex / Gemini inside Obsidian | 🤔 Forum plugin, Nov 2025 |

## Maybe
| Plugin | What It Does | Status |
|--------|-------------|--------|
| **Obsidian Git** | Auto-commit vault to git repo | 🤔 For version control + VPS sync? |
| **Webclipper** | Clip web pages into vault | 📝 SSP uses it for LinkedIn contacts |
| **DB Folder** | Database-like folder views | 🤔 Alternative to Dataview |

## Research Needed
- Compare Dataview vs Bases for our use case
- Test Kanban plugin vs Bases kanban view
- Evaluate sync options: Git vs rclone vs Obsidian Sync ($)
