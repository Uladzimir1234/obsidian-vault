---
type: source
platform: documentation
url: "https://wiki.sascha-kasper.com/obsidian/lean-vaults/lean-crm/lean-productivity-crm-vault/"
date_found: 2026-02-28
relevance: high
has_downloadable_vault: true
tags: [source, pattern, crm, entity-model, template]
---

# LeanProductivity CRM Vault — Ready-Made Template

## Why Relevant
Complete downloadable CRM vault with 5 entities, templates, folder structure, and plugins pre-configured. Most structured CRM implementation found.

## 5 Entity Model
1. **Accounts** — main entity (company or person buying)
2. **Contacts** — people related to Account
3. **Opportunities** — deals, linked to Account + Products
4. **Products** — what you sell, linked to Opportunities
5. **Interactions** — meetings/calls, linked to Contacts + Opportunities

## Relationships
```
Account ← 1:many → Contacts
Account ← 1:many → Opportunities
Opportunity ← many:many → Products
Interaction ← many:1 → Contact
Interaction ← many:1 → Opportunity
```

## Vault Contents
- CRM-specific folder structure
- Templates for all 5 entities
- Pre-defined file classes
- Required plugins pre-installed
- CSS snippets for styling
- Quick action buttons (Add Account, Add Contact, etc.)
- Lookup tables (Account Types, Opp Phases, Probabilities, Product Types)

## Folder Structure
```
90 Organize/
├── Bases/CRM/
│   ├── Accounts/
│   ├── Contacts/
│   ├── Interactions/
│   ├── Opportunities/
│   └── Products/
├── Classes/CRM/ (file class definitions)
├── Embeddable Elements/CRM/ (buttons, quick actions)
├── Lookups/CRM/ (dropdowns: Account Sizes, Opp Phases, etc.)
└── Templates/CRM/ (one per entity type)
```

## 💡 Takeaways for DECA
- 5-entity model maps perfectly to DECA: Account=Customer, Opportunity=Deal, Product=S8000/LINEAR
- **Lookup tables** for dropdowns = standardized data entry (stage names, product types)
- **Embeddable buttons** = quick "Add new..." actions
- **File classes** = enforce consistent structure per entity type
- Consider downloading and studying this vault as base
- The `Interaction` entity being linked to BOTH Contact AND Opportunity = powerful for tracking which conversations affected which deals
