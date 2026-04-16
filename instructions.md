# Ask Microsoft Re-design -- AI Instructions

## Project Overview
This is a **UX prototype** for redesigning the "Ask Microsoft" welcome greeting / chatbot widget used on microsoft.com for Microsoft 365 sales-assist. The prototype is built as a **single-file HTML page** with inline CSS and JS -- no build tools, no frameworks. It is shared with stakeholders via GitHub Pages.

## Design System
- **Microsoft Fluent 2** design language (colors, typography, spacing, border radii, shadows)
- Primary font: `Segoe UI Variable`, `Segoe UI`, system fallback stack
- Primary brand color: `#0F6CBD` (Fluent blue)
- Accent gradient bar: linear-gradient of blues along the left sidebar and input bar
- Embossed header buttons with subtle box-shadow and border (Fluent 2 "subtle" pattern)

## Architecture
- **Single file:** `index.html` -- all CSS and JS inline
- **Assets:** `icon.jpg` (Ask Microsoft logo), `robots.txt`
- **Sources folder:** reference screenshots and materials
- **Hosted on GitHub Pages** from `sunilmsft` personal account

## Design Variants (Tabs)
| Tab | Name | Description |
|-----|------|-------------|
| A | Streamlined | Full paragraph greeting, lowest friction |
| B | Chip-Based | Short greeting + interactive chips |
| C | Card-First | Minimal greeting + collapsible capability card + one-time consent modal |
| D | Best-Of Hybrid | Combines best of A+B+C: minimal greeting + chips + subtle opt-out |
| E | AI-Native | Task-based entry cards (2x3 grid), contextual follow-up chips, human handoff bar, voice input, inline actions |
| S | Summary | Comparison tables + competitive analysis (Intercom, Zendesk, Salesforce) |

## Chat Engine
- Keyword-based KB matching (no API calls -- fully static prototype)
- M365 plan data sourced from microsoft.com
- Features: thumbs feedback, typing indicator, contextual chips (E only), human handoff bar (E only), inline action buttons (E only)

## Key Components
- **Header:** Logo, "Ask Microsoft" title, callback popover, phone popover (click-to-call + copy), reset, close
- **Starter prompts (E):** 2x3 task-grid with compact text-only cards (icons removed)
- **Chips (B, D):** Inline SVG icon + label, `#0F6CBD` themed
- **Consent:** Varies per option (opt-out link, toggle card, modal, or inline)
- **Transparency FAQ:** Always accessible, placement varies per option
- **Footer:** AI disclaimer + input bar with gradient accent

## Coding Rules
- Keep everything in a single HTML file (inline CSS + JS)
- Use HTML entities for all non-ASCII characters (no raw Unicode)
- Validate JS with `node --check` after edits
- Use ASCII-safe file content -- avoid UTF-8 BOM issues
- All CSS is minified single-line per rule
- No external dependencies (CDN, npm, etc.)

## Deployment
- Git repo in workspace folder
- Push to `sunilmsft` GitHub for Pages hosting
- "Save" means: git commit+push, copy to OneDrive, update memory files
