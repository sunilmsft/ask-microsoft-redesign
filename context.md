# Ask Microsoft Re-design -- Project Context

## What This Is
A high-fidelity interactive prototype of the "Ask Microsoft" chatbot welcome experience. Used for internal UX review with stakeholders. This is NOT production code -- it is a clickable demo that simulates how the chat widget would look and behave.

## Business Context
- **Product:** Ask Microsoft -- the AI chatbot on microsoft.com for M365 sales and support
- **Goal:** Redesign the welcome greeting to reduce friction, increase engagement, and modernize the experience
- **Audience:** Internal Microsoft stakeholders (Marketing Engineering, eCommerce team)
- **Review period:** April 2026

## File Structure
```
index.html          -- Main prototype (single-file, self-contained)
icon.jpg            -- Ask Microsoft chat logo
robots.txt          -- Prevents indexing of prototype
Sources/            -- Reference screenshots and design materials
instructions.md     -- Coding rules, design system, architecture
context.md          -- This file: business context, structure, decisions
memory.md           -- Progress log, change history, decisions made
```

## Design Decisions Made
1. **Fluent 2 design system** -- matches Microsoft brand, professional look
2. **Single-file architecture** -- fast iteration, easy GitHub Pages deploy
3. **5 design variants + summary** -- gives stakeholders real choices to compare
4. **Static KB engine** -- no API needed, showcases realistic conversation flow
5. **Option E (AI-Native) as the leading variant** -- task-based cards, contextual chips, human handoff
6. **Competitive analysis included** -- Intercom, Zendesk, Salesforce comparison in Summary tab

## Key UX Elements Across All Variants
- Request a callback (header popover linking to MS form)
- Call us: (800) 642-7676 with click-to-call and copy
- Transparency FAQ link (always accessible)
- Transcript consent (opt-out mechanism)
- AI disclaimer footer
- Thumbs up/down feedback on bot messages
- Typing indicator animation
- Gradient accent bar (input + sidebar)

## Option E Specific Features
- 2x3 task-grid starter prompts (text-only, no icons -- compact professional look)
- Contextual follow-up chips that change based on detected topic
- Human handoff bar appears after 2 exchanges
- Inline action buttons (CTA cards within responses)
- Voice input (mic icon)
- AI/Classic toggle for A/B comparison

## Data Source
- M365 plan pricing and features from microsoft.com/en-us/microsoft-365/
- Plans: Free ($0), Basic ($19.99/yr), Personal ($99.99/yr), Family ($129.99/yr), Premium ($199.99/yr)
