# Ask Microsoft Redesign — Changelog

## How This Works

- Each **version** is a milestone snapshot tagged in Git
- To **view** any version: `git checkout v4` (then `git checkout master` to return)
- To **revert** the UI: `git checkout v6-baseline -- index.html`
- To **compare** versions: `git diff v4 v6 -- index.html`
- Nothing is ever deleted — all previous versions are permanently preserved

---

## Version Summary

A quick overview of how the prototype evolved. Scroll down for the detailed changelog.

| Version | Tag | Date | One-line summary |
|---------|-----|------|-----------------|
| **v1** | `v1` | Apr 14 | Initial prototype: 4 chat variants side by side, Fluent 2 design |
| **v2** | `v2` | Apr 14 | Visual polish: header styling, transparency badge, competitor analysis |
| **v3** | `v3` | Apr 14 | New AI-Native variant (Option E) with guided conversation flow |
| **v4** | `v4` | Apr 16 | Starter prompt redesign, guided Q&A flows for plans/trial/Copilot, handoff bar |
| **v5** | `v5` | Apr 17 | Consolidate to 3 tabs, add email transcript capture, sequence system nudges |
| **v6** | `v6` | Apr 17 | Business-only focus, intent-based handoff gate, context-aware replies |
| **v6-baseline** | `v6-baseline` | Apr 17 | Baseline snapshot before layout refinements |
| **v7** | `v7` | Apr 17 | Layout and compliance refinement — reduce bottom clutter, preserve compliance |
| **v7.2** | `v7.2` | Apr 17 | Bottom area declutter — focused input, email moved to inline, data usage below input |
| **v7.3** | `v7.3` | Apr 17 | Fixed Proactive vs Passive toggle regression — modes now behave correctly |
| **v7.4** | `v7.4` | Apr 17 | Restored Always On icon, made Proactive vs Passive visibly distinct |

---

## Detailed Changelog

### v1 — Initial Prototype (Apr 14)
*Tag: `v1` · Commit: `2af5a4e`*

| Area | What changed | Why |
|------|-------------|-----|
| Full prototype | Created 4 chat design variants (A/B/C/D) with an interactive Microsoft 365 knowledge base | Establish baseline options for stakeholder review |
| Layout | Right-docked full-height panel with reset button | Match real Ask Microsoft sidebar positioning |
| Design system | Adopted Microsoft Fluent 2 — blue primary, Segoe UI Variable font, elevation shadows | Align with Microsoft's current design language |
| Messages | Added thumbs up/down feedback buttons inside bot responses | Let users signal whether responses were helpful |
| Identity | Real Ask Microsoft icon, rounded-square logo, curved panel edges | Match production Ask Microsoft look and feel |
| Spacing | Compact layout — tighter padding, smaller fonts, single-line chips | Fit content comfortably in narrow sidebar width |

---

### v2 — Visual Polish (Apr 14)
*Tag: `v2` · Commit: `0479675`*

| Area | What changed | Why |
|------|-------------|-----|
| Transparency | Added "Transparency FAQ" badge with shield icon on its own line | Clear compliance/trust signal without cluttering the greeting |
| Header | Refined header styling — tested 3D gradient, then softened to neutral | Stronger brand presence, but pulled back when it got distracting |
| Chips | Restyled suggestion chips from bold 3D to subtle white pills | Chips were competing visually with the actual messages |
| Summary tab | Added competitive UX analysis table comparing Ask Microsoft to peers | Help stakeholders see how we compare to Apple, Google, Amazon support |

---

### v3 — AI-Native Variant (Apr 14)
*Tag: `v3` · Commit: `2af5a4e`*

| Area | What changed | Why |
|------|-------------|-----|
| New variant | Added Option E: an AI-first assistant with guided welcome, contextual chips, human offramp, inline actions, and voice input | Test a conversational approach vs. the traditional menu-based options |
| AI disclosure | Added avatar, "AI assistant" label, and warm greeting text | Build trust by clearly identifying the chatbot as AI |

---

### v4 — Guided Flows & Prompts (Apr 16)
*Tag: `v4` · Commit: `4203e1d`*

| Area | What changed | Why |
|------|-------------|-----|
| Starter prompts | Iterated through 4 designs: bold accent → subtle borders → card grid → pill-shaped | Finding the right visual weight — not too loud, not invisible |
| Prompt variants | Added a toggle to switch between baseline and enhanced prompt styles | Let stakeholders compare approaches side by side |
| Welcome | Tested 3 greeting tones (warm, friendly, confident) with "AI agent" label | Determine which voice resonates best for business |
| Guided plans flow | Multi-step Q&A: "How many people?" → "What do you need?" → personalized recommendation | Help users find the right plan through conversation, not browsing |
| Guided flows | Added trial, Copilot, and troubleshoot conversation paths | Cover all four major user intents with guided experiences |
| Handoff bar | "Want to talk to someone?" bar appears after 2 turns with 1.5s fade-in | Provide a human escalation path at a natural pause point |

---

### v5 — Consolidation & Email Capture (Apr 17)
*Tag: `v5` · Commit: `66f0463`*

| Area | What changed | Why |
|------|-------------|-----|
| Tab structure | Consolidated from 5 tabs down to 3: Recommended★, Baseline, Chips + Summary | Too many tabs — stakeholders had comparison fatigue |
| Email capture | Added "Email me a copy" feature with two modes: Proactive (system offers) and Passive (user clicks icon) | Integrate transcript-summary-in-email from the consent-ux-prototype |
| Handoff styling | Made "Keep exploring with AI" the primary blue button; "Talk to a person" became a subtle underlined link | Reinforce AI-first positioning — human escalation is available but not pushed |
| Nudge sequencing | System nudges now appear one at a time — email capture only after handoff bar is dismissed | Previously, handoff bar + email capture stacked simultaneously and overwhelmed the user |

---

### v6 — Business-Only Focus (Apr 17)
*Tag: `v6` · Commit: `bf59346`*

| Area | What changed | Why |
|------|-------------|-----|
| All content | Rewrote entire knowledge base for business: Basic ($6/user/mo), Standard ($12.50), Premium ($22), Enterprise (E3/E5), Copilot add-on ($30) | Ask Microsoft serves business customers, not consumers |
| Guided flow | First question is now "How large is your organization?" → Small (1-25) / Mid-size (25-300) / Large (300+) | Segment by business size to recommend the right plan |
| Consumer redirect | Personal, student, family queries now get: "For home plans, visit microsoft365.com" | Don't mislead consumers — redirect them gracefully |
| Handoff gate | Triggers on intent signals (enterprise, pricing, buy, license) instead of turn count | Appears when the user actually needs it, not at an arbitrary moment |
| Handoff timing | Gate appears BEFORE the AI response — user decides first, then sees content | Eliminates stacking — clean decision point |
| Welcome cards | Business-focused: compare plans, free trial, Copilot for business, security, licensing | Match the audience walking into a business support chat |
| Context awareness | Chat remembers org size — follow-up questions get direct answers, not repeated questions | "Compare plans" chip no longer re-asks "How large is your org?" |
| Icons | Switched to clean stroke-based icons (1.8px weight) for header | Previous filled icons were unreadable blobs at 16px |
| Email placement | Moved "Email me a copy" to footer bar, next to AI disclaimer | Header was too crowded (wrapping title); FAQ line was misleading |

---

### v7 — Layout and Compliance Refinement (Apr 17)
*Tag: `v7` · Commit: `3a37a3b`*

| Area | What changed | Why |
|------|-------------|-----|
| Transparency FAQ | Moved from bottom of chat to just below the greeting, above starter prompts/chips | Reduce bottom clutter — FAQ was buried below opt-out and competing with the input area |
| FAQ styling | Smaller text (10.5px), lighter color (#999), info circle icon | Secondary element — visible but not competing with the greeting or prompts |
| Bottom cleanup | Removed Transparency FAQ and opt-out text from the chat body bottom | Only input field, mic, and send button remain below the conversation |
| Compliance text | "AI-generated content may be incorrect" stays just above input; "We may save conversations" moved to footer as subtle line | Both compliance elements preserved and visible, but no longer cluttering the chat area |
| Opt-out | Moved from chat body to footer — same click behavior, lighter styling | Keeps opt-out accessible without visual noise in the conversation |
| All 3 widgets | Same refinement applied to Recommended (A), Baseline (B), and Chips (C) | Consistent layout across all variants |

---

### v7.2 — Bottom Area Declutter (Apr 17)
*Tag: `v7.2` · Commit: `4a38937`*

| Area | What changed | Why |
|------|-------------|-----|
| Footer hierarchy | Reordered to: AI disclaimer → input field → data usage line | Input is now the focal point — nothing competes with it |
| AI disclaimer | "AI-generated content may be incorrect" centered above input, 10px, lighter color | Visible but minimal — sets context without dominating |
| Data usage text | "We may save conversations... Opt out" moved below input | Footer-like treatment (9.5px, #bbb) — present but unobtrusive |
| Email me a copy | Removed from initial footer area | Was competing for attention next to the input field |
| Passive email mode | Now shows inline card after first bot response instead of in footer | Appears only when there’s content worth saving — not on empty screen |
| Dead CSS removed | Removed `.save-btn` styles (button no longer in footer) | Cleanup unused code |

---

### v7.3 — Fix Proactive vs Passive Toggle (Apr 17)
*Tag: `v7.3` · Commit: `41498b9`*

| Area | What changed | Why |
|------|-------------|-----|
| Toggle reset | Switching modes now resets the chat to a clean state | Previously, old turns/state persisted so the new mode couldn’t demonstrate its behavior |
| Passive trigger | Changed from `eTotalTurns === 1` to `eTotalTurns >= 1` with dedup guard | Old check only fired on the very first turn — switching mid-conversation meant passive never triggered |
| State cleanup | `setEmailMode` now resets `eTotalTurns`, `eMsgCount`, `handoffDismissed`, `handoffGateShown`, `guidedAnswers`, and `emailCaptureShown` | All email and handoff state must be fresh for the mode switch to take effect |
| Dead code | Removed `saveBtn` reference from `resetChat` | Button was removed in v7.2 but reference lingered |
| Mode behavior | **Proactive**: email card appears after handoff is dismissed + next exchange. **Passive**: email card appears inline after the first bot response. | Two clearly distinct experiences that stakeholders can toggle and compare |

---

### v7.4 — Restore Always On Icon + Distinct Mode Behavior (Apr 17)
*Tag: `v7.4`*

| Area | What changed | Why |
|------|-------------|-----|
| Always On icon restored | Re-added "Email me a copy" button to cwE footer with `.save-btn` CSS | Was deleted in v7.2 — this button is the whole point of Passive mode ("customer taps Save when ready") |
| Passive mode — new behavior | Footer button appears after first exchange; user clicks it whenever ready; no system-initiated card | Passive = user-initiated. Persistent button is the differentiator — not a timed card |
| Proactive mode — unchanged | No footer button visible; system shows "Want a copy?" card after handoff dismissed + next exchange | Proactive = system-initiated. Card only appears at the right moment in the conversation |
| Button visibility | `showPassiveButton()` shows the footer button only in Passive mode after first exchange; hidden in Proactive | Proactive users never see the button; Passive users always have it available |
| Toggle reset | `setEmailMode` now hides the button, resets chat, resets all state | Clean demo of each mode from scratch |
| `resetChat` | Re-added `saveBtn` hide on reset | Button must disappear when conversation resets |
| Root cause | v7.3 fixed state reset but both modes still produced the same inline card — no visual distinction | The real differentiator was the persistent footer icon (Passive) vs system card (Proactive), not timing of the same card |

---

### v6-baseline — Pre-Refinement Snapshot (Apr 17)
*Tag: `v6-baseline` · Commit: `60fc864`*

Same UI as v6. This tag marks the deployed state before the v7 layout refinement. Use this to revert if needed.

```
git checkout v6-baseline -- index.html
```

---

## Version Tags → Commit Map

| Tag | Commit | Description |
|-----|--------|-------------|
| `v1` | `2af5a4e` | Initial prototype: 4 variants, Fluent 2, interactive chat |
| `v2` | `0479675` | Header polish, transparency pill, competitive analysis |
| `v3` | `2af5a4e` | AI-Native variant (Option E) added |
| `v4` | `4203e1d` | Starter prompt iterations, guided flows, handoff bar |
| `v5` | `66f0463` | 3-tab consolidation, email capture, sequenced nudges |
| `v6` | `bf59346` | Business-only focus, intent-based handoff gate |
| `v6-baseline` | `60fc864` | Pre-refinement snapshot — safe revert point |
| `v7` | `3a37a3b` | Layout and compliance refinement |
| `v7.2` | `4a38937` | Bottom area declutter |
| `v7.3` | `41498b9` | Fix Proactive vs Passive toggle |
| `v7.4` | *(pending)* | Restore Always On icon + distinct mode behavior |

---

## Quick Reference

```bash
git tag                          # list all versions
git checkout v4                  # view v4 snapshot
git checkout master              # return to latest
git checkout v6-baseline -- index.html   # revert UI to baseline
git diff v4 v6 -- index.html    # compare two versions
```
