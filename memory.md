# Ask Microsoft Re-design -- Progress & Memory

## Change Log

### April 16, 2026
- **Starter prompts (Option E):** Removed colored icon squares from the 2x3 task-grid cards. Now text-only with bold title + subtitle. More compact (7px/10px padding, 5px gaps) and professional. `.tc-icon` elements hidden via `display:none`.
- **Created project docs:** Added `instructions.md` (coding rules, design system), `context.md` (business context, decisions), `memory.md` (this file -- progress tracking).

## Current State
- All 5 design variants (A-E) functional and interactive
- Summary tab with comparison tables and competitive analysis complete
- Option E is the leading/recommended variant
- Starter prompts in E are text-only, compact, professional
- Chat engine with M365 KB is fully functional (static, keyword-based)
- All contextual features working: follow-up chips, handoff bar, inline actions, voice icon

## Known Decisions
- Icons removed from Option E starter prompts (per stakeholder feedback: "make nicer and more compact")
- Option D uses action-verb chips ("Which plan fits me?" vs "Compare plans")
- Consent is non-blocking in recommended variants (D, E)
- Human handoff bar triggers after 2 exchanges in E

## Pending / Future Ideas
- [ ] Stakeholder review of icon-free starter prompts
- [ ] Consider even shorter greeting text (Salesforce-style brevity)
- [ ] Page-context-aware chip suggestions (identified as competitive gap)
- [ ] Post-conversation "Was this helpful?" flow
- [ ] Tooltip or label on first visit for callback/phone header icons
- [ ] Deploy latest to GitHub Pages

## Tech Notes
- PowerShell UTF8NoBOM encoding required for writing files
- HTML entities for all non-ASCII (no raw Unicode in source)
- Always validate JS with `node --check index.html` is not applicable -- use browser console
- OneDrive-synced workspace: quote paths with spaces in terminal commands
