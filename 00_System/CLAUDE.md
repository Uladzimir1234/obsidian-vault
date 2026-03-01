# CLAUDE.md — Agent Instructions

This is the **DECA Euro Windows & Doors** business vault — a production CRM and knowledge base in Obsidian.

## Vault Structure
- `00_System/` — Templates, guides, this file
- `01_Customers/` — One note per customer/lead
- `02_Sellers/` — Team profiles (Eric, Paul, Ilya)
- `03_Products/` — Product specs (GEALAN profiles)
- `04_Deals/` — One note per deal/opportunity
- `05_Interactions/` — Call logs, email summaries
- `06_Knowledge/` — Sales playbooks, objection handling, processes
- `07_Analytics/` — Reports, insights, patterns
- `08_Inbox/` — Quick capture, unsorted notes
- `09_Research/` — Archived research from vault design phase

## Rules for Creating Notes

1. **Always add YAML frontmatter** with at minimum: `type`, `status`, `created`, `tags`
2. **Use wiki-links**: `[[Note Name]]` or `[[02_Sellers/Eric Yurtuc]]`
3. **Link related entities**: Customer → Deals, Interactions, Seller. Deal → Customer, Products, Seller.
4. **Use templates** from `00_System/Templates/` for new notes
5. **No spaces in folder names** — use underscores or hyphens

## Linking Conventions
- Customer notes should link to their deals, interactions, and assigned seller
- Deal notes link to customer, products, and seller
- Interaction notes link to customer, deal, and seller
- Use `[[tags]]` for cross-cutting themes

## Frontmatter Example
```yaml
---
type: customer
status: active
created: 2025-03-01
tags: [residential, boston]
---
```
