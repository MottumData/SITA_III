# SITA III — Claude Code Context

## Project
Suriname Cruise Services Catalogue for SITA (Suriname Investment & Trade Agency).
GitHub Pages static site: https://mottumdata.github.io/SITA_III/

## Architecture
- `index.html` — single-file SPA (HTML + CSS + JS, no framework, no build step)
- `data/` — source HubSpot CRM CSV exports
- `Context/` — project knowledge, dummy prototype, form questionnaire
- `DESIGN.md` — full design system specification

## Data source
All provider data lives in `data/hubspot-crm-exports-cruises-services-companies-2026-04-07.csv`.
The JavaScript `DATA` array in `index.html` is hand-mapped from this CSV.
When new companies are added to HubSpot, they need to be manually added to the DATA array.

## Design System
Always read DESIGN.md before making any visual or UI decisions.
All font choices, colors, spacing, and aesthetic direction are defined there.
Do not deviate without explicit user approval.
In QA mode, flag any code that doesn't match DESIGN.md.

## Skill routing

When the user's request matches an available skill, ALWAYS invoke it using the Skill
tool as your FIRST action. Do NOT answer directly, do NOT use other tools first.

Key routing rules:
- Bugs, errors, "why is this broken", 500 errors → invoke investigate
- Ship, deploy, push, create PR → invoke ship
- QA, test the site, find bugs → invoke qa
- Code review, check my diff → invoke review
- Design system, brand → invoke design-consultation
- Visual audit, design polish → invoke design-review
- Save progress, checkpoint, resume → invoke checkpoint
- Code quality, health check → invoke health
