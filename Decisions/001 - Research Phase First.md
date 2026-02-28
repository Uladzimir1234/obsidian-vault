---
type: decision
number: 1
date: 2026-02-28
status: decided
tags: [decision, process]
---

# Decision 001: Research Phase Before Building

## Context
We have a working CRM system (decacrm.com + HubSpot + Command Center). Adding Obsidian is a strategic layer, not a replacement.

## Decision
**Research and design the Obsidian architecture BEFORE building the actual CRM vault.**

This vault (`decacrm obsidian implement brainstorm`) is the research workspace. We collect:
- Reddit examples
- YouTube tutorials
- NotebookLM analysis
- Article summaries
- Architecture patterns

Only when the design is solid do we build the production vault.

## Why
- Obsidian architecture choices are hard to change later (folder structure, entity model, naming conventions)
- Multiple valid approaches exist — we need to pick the right one for DECA
- Better to learn from others' mistakes first
- Vlad wants to participate in design decisions (not just see results)
