# Ask Microsoft Redesign — Changelog

## Versioning

- **Git tags** mark each version: `git tag` to list, `git checkout v5` to view any version
- **Revert**: `git checkout v3 -- index.html` restores v3's index.html into your working tree
- **Compare**: `git diff v3 v5 -- index.html` shows exactly what changed between versions
- Every version is preserved in git history — nothing is overwritten

---

## Changelog

| Version | Date | Area | Change | Before | After | Why |
|---------|------|------|--------|--------|-------|-----|
| **v1** | Apr 14 | Full prototype | Initial 4-variant chat UI with interactive M365 knowledge base | — | 4 design options (A/B/C/D) with chat engine, KB, GitHub Pages deploy | Establish baseline for stakeholder review |
| v1 | Apr 14 | Layout | Full-height right-docked panel, reset button, z-index fix | Floating panel, no reset | Docked panel, reset conversation | Match real Ask Microsoft positioning |
| v1 | Apr 14 | Design system | Migrate to Microsoft Fluent 2 (colors, typography, shadows) | Generic styling | Fluent 2: `#0F6CBD` primary, Segoe UI Variable, elevation tokens | Align with Microsoft design language |
| v1 | Apr 14 | Messages | Thumbs up/down inside bot cards, interactive voting | No feedback UI | Inline thumbs with highlight/dim on click | Enable response feedback pattern |
| v1 | Apr 14 | Identity | Rounded-square logo, curved panel edges, actual Ask Microsoft icon | Placeholder logo | Real icon + matching border radius | Match production Ask Microsoft identity |
| v1 | Apr 14 | Spacing | Compact padding, smaller fonts, single-line chips, gradient input underline | Loose layout | Tight, polished layout | Fit more content in sidebar width |
| v1 | Apr 14 | Tabs | Summary tab fix, AI disclaimer right-aligned | Summary hidden behind chat | Proper z-index + padding-right on tabs | All tabs accessible |
| **v2** | Apr 14 | Transparency | FAQ pill with shield icon on its own line | Wordy preamble text | Clean pill below greeting | Reduce clutter, match compliance pattern |
| v2 | Apr 14 | Header | Larger logo/title, 3D gradient bar, embossed circular buttons | Flat header | Subtle gradient + embossed buttons | Stronger brand presence |
| v2 | Apr 14 | Header | Soften to neutral gradient — buttons blend naturally | Over-styled 3D | Neutral gradient, softer circles | Too aggressive — distracting from content |
| v2 | Apr 14 | Chips | Embossed 3D style → refined white bg rounded-rect | Bold 3D chips | Subtle white pills matching message style | Chips competed with messages visually |
| v2 | Apr 14 | Summary | Competitive UX analysis table + action-oriented chip labels on D | Basic summary | Competitor comparison + improved labels | Help stakeholders understand competitive landscape |
| **v3** | Apr 14 | New variant | Option E: AI-Native Assistant with guided welcome, contextual chips, human offramp, inline actions, voice UI | 4 variants (A-D) | 5th variant E with conversational flow | Test AI-first approach vs traditional options |
| v3 | Apr 14 | Option E | Identity block, AI disclosure in greeting, simplified capability text | Raw welcome | Avatar + "AI assistant" label + warm nudge | Build trust with clear AI labeling |
| **v4** | Apr 16 | Starter prompts | Polish cycle: blue accent → subtle borders → visible+subtle border | Bold blue left accent | `#d1d1d1` border, blue on hover | Iterated to find right visual weight |
| v4 | Apr 16 | Starter prompts | Baseline/enhanced variants with v1/v2 toggle | Single version | Two switchable variants | Let stakeholders compare approaches |
| v4 | Apr 16 | Starter prompts | v3 guided entry: hero card + pill secondaries → uniform grid → pill-shaped → borderless shadow | Multiple iterations | Polished card grid with elevation | Explored 4 layout approaches to find best balance |
| v4 | Apr 16 | Welcome | 3 greeting variations (warm/friendly/confident), AI agent label | Single greeting | 3 tone variations, "AI agent" framing | Test different voice/tone for business users |
| v4 | Apr 16 | Guided flows | Plan recommendation: clarifying questions → personalized recommendation | Static plan info | Multi-step guided conversation with choices | Help users find the right plan through conversation |
| v4 | Apr 16 | Guided flows | Trial, Copilot, and troubleshoot guided paths | Plan flow only | 4 complete guided conversation trees | Cover all major user intents |
| v4 | Apr 16 | Handoff | Handoff bar with 1.5s delay fade-in after response | No escalation path | "Want to talk to someone?" bar after 2 turns | Provide human offramp at natural moment |
| **v5** | Apr 17 | Structure | Consolidate to 3 tabs: Recommended★, Baseline, Chips + Summary | 5 tabs (A-E) | 3 tabs + Summary, cleaned dead code | Reduce comparison fatigue for stakeholders |
| v5 | Apr 17 | Email capture | Proactive vs passive transcript-in-email with toggle in info card | No email capture | Two-mode system: auto-prompt or header icon | Integrate consent-ux-prototype v4 pattern |
| v5 | Apr 17 | Email capture | Fix proactive trigger: count all turns (incl. guided choices) | Never triggered (only counted free-text) | `eTotalTurns` counter for all exchanges | Guided flows are mostly choice buttons — old counter missed them |
| v5 | Apr 17 | Header | Move save/email icon to header bar with envelope, match Fluent style | Footer floppy disk icon | Header envelope circle button | Floppy disk dated, footer placement ignored |
| v5 | Apr 17 | Handoff | AI-first hierarchy: "Keep exploring with AI" primary, "Talk to a person" as underlined text link | Both as equal buttons | AI = blue primary, person = subtle link | Reinforce AI-first positioning |
| v5 | Apr 17 | Sequencing | Sequence nudges: email capture only after handoff dismissed + 1 more turn | Handoff + email stacked simultaneously | One nudge at a time, gated by `handoffDismissed` flag | Too many things happening at once — overwhelming |
| **v6** | Apr 17 | KB / Content | Business-only focus: plans, pricing, guided flows all rewritten | Consumer plans (Personal/Family/Premium) | Business Basic/Standard/Premium + Enterprise, per-user pricing | Ask Microsoft is for business customers only |
| v6 | Apr 17 | Guided flow | Org size → priorities → recommendation (Small/Mid/Enterprise) | "Just me / Family / Team" | "Small 1-25 / Mid-size 25-300 / Large 300+" | Business audience segmentation |
| v6 | Apr 17 | Handoff | Intent-based handoff gate: triggers on enterprise, pricing, buy signals | Turn-count trigger (eMsgCount===2) | Intent detection + gate BEFORE response | Contextual — appears when user actually needs it |
| v6 | Apr 17 | Handoff | Gate pauses before AI response: "Keep exploring" reveals queued answer | Bar appended after response | Decision gate before response shown | No stacking — user chooses first, then sees content |
| v6 | Apr 17 | Welcome | Business-focused task cards: compare business plans, Copilot for business, security, licensing | Consumer prompts (student, personal) | Business prompts (plans, trial, Copilot, security, licensing) | Match business audience |
| v6 | Apr 17 | Context chips | Business-aware chips: security, enterprise, licensing topics | Consumer topics (student, family, premium) | Business topics with contextual suggestions | Chips now match business KB |
| v6 | Apr 17 | Consumer redirect | Redirect for personal/student/family/home queries | Consumer plans shown | "For home plans, visit microsoft365.com" with link | Don't mislead consumers — redirect gracefully |
| v6 | Apr 17 | Email icon | Move from header to footer disc line | In header (caused word wrap) | Footer: "AI-generated content..." + "Email me a copy" | Header too crowded — wrapped "Ask Microsoft" |
| v6 | Apr 17 | Email icon | Remove from FAQ line (looked like FAQ email option) | Next to Transparency FAQ with `\|` separator | Own section in footer disc bar | Misleading — looked like "email the FAQ" |
| v6 | Apr 17 | Context | Context-aware `findReply`: skip re-asking org size if already answered | "Compare plans" chip re-asked org size | Direct comparison table when org size known | Broke conversational flow — felt like amnesia |
| v6 | Apr 17 | Icons | Clean stroke-based icons at 16px, 1.8 weight | Filled Fluent blobs (chunky at 16px) | Stroke-based: phone, callback+rings, arrow reset | Filled icons were unreadable at small size |

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

---

## How to Use

### View a previous version
```bash
git checkout v4          # switch to v4 snapshot
git checkout master      # return to latest
```

### Restore a specific file from a previous version
```bash
git checkout v4 -- index.html    # restore v4's index.html
git diff HEAD index.html         # see what changed
git checkout HEAD -- index.html  # undo if you don't want it
```

### Compare versions
```bash
git diff v4 v6 -- index.html    # see all changes between v4 and v6
git diff v5 v6 -- CHANGELOG.md  # compare changelog entries
```

### List all versions
```bash
git tag                          # list all version tags
git log --oneline v4..v6         # list commits between v4 and v6
```
