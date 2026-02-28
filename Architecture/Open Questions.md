---
type: architecture
tags: [question, architecture]
---

# Open Questions

## Entity Model
- [ ] How many entity types? (3 minimal vs 5 full — see [[LeanProductivity CRM Vault]])
- [ ] Separate Interaction files or inline in Customer page? (see [[General Contractor CRM]])
- [ ] Products as entities with pricing or just reference docs?
- [ ] Quotes as generated files or template-based?

## Plugins
- [ ] **Dataview vs Obsidian Bases** — which for structured queries? (Bases is newer, built-in)
- [ ] **Templater** — needed for dynamic templates?
- [ ] **Kanban** — or use Bases kanban view?
- [ ] **Calendar** — for interaction timeline?
- [ ] Any other essential plugins?

## AI Integration
- [ ] How does Klawdiy read/write to vault? (filesystem access vs API)
- [ ] Sync mechanism: rclone? Git? Obsidian Sync?
- [ ] How do agents know vault conventions? (install [[Obsidian Agent Skills - Official]])
- [ ] Auto-populate from HubSpot/Quo or manual + AI-assisted?

## Folder Structure
- [ ] Flat (all customers in one folder) vs nested (by stage, by seller)?
- [ ] Where do daily notes go?
- [ ] How to handle archived/closed deals?

## Sync & Access
- [ ] Google Drive sync for Vlad's phone access?
- [ ] VPS ↔ Drive ↔ Obsidian mobile — what's the sync chain?
- [ ] Conflict resolution if Vlad edits on phone while agent edits on server?

## Pricing & Quotes
- [ ] How to structure product pricing data for quote generation?
- [ ] Quote template format — markdown table? Special template?
- [ ] Multiple quote versions per customer — how to track?
