---
name: write-specs
description: >
  Write clear, shipworthy product specs — PRDs, feature briefs, RFCs, design
  docs, one-pagers, and architecture decision records — from scratch, rough
  notes, or existing drafts. Always use this skill when someone says "write a
  spec for X", "turn my notes into a PRD", "help me spec this feature", "what
  should go in my RFC", "write a product brief", "document this design
  decision", "I need to write up a feature", "draft a requirements doc", or
  any variation of wanting to produce a written spec, brief, or design doc.
  Also trigger when someone shares a rough idea or meeting notes and asks to
  turn it into something shareable. Guides users through structure discovery
  — generates 3 spec skeleton previews and lets them pick, instead of asking
  them to describe format in the abstract. Produces clean Markdown that
  actually gets read.
---

# Write Specs

Turn rough ideas, meeting notes, or blank-page anxiety into clear product
specs that actually get read and actioned.

## Core Principles

- **Structure before content** — The right skeleton matters more than perfect
  prose. Surface structure options first; let the user pick what fits their
  mental model.
- **Show, don't tell** — Generate 3 skeleton previews rather than asking
  "what format do you prefer?" in the abstract. People know what they like
  when they see it.
- **Write for the reader** — Every section earns its place by answering a
  question a reader would actually ask. Kill filler, kill padding.
- **Stage-appropriate depth** — Early-stage specs answer *why*. Mid-stage
  answer *what*. Pre-build answer *how*. Don't write a pre-build spec for an
  idea you haven't validated yet.

---

## Phase 0: Detect Mode

Identify the mode before doing anything else:

- **Mode A — New spec from scratch** → Phase 1
- **Mode B — Convert notes/dump** → Phase 1 (use their notes to pre-fill
  your interview answers; only ask what's genuinely missing)
- **Mode C — Improve existing spec** → Read it, identify gaps (use
  references/ship-checklist.md), then go directly to Phase 3 with a
  proposed revision
- **Mode D — Just the structure, I'll write it** → Skip to Phase 2, generate
  skeletons, let them pick, output the skeleton only

---

## Phase 1: Content Discovery

Ask all questions in a single message. The goal is to understand enough to
generate the right 3 skeletons — not to gather every detail upfront.

1. **Spec type**: Feature PRD · Technical RFC · Design decision doc ·
   Architecture overview · One-pager brief · API/integration spec
2. **Audience**: Engineering-only · Mixed (eng + design + PM) · Exec ·
   External (customers, partners)
3. **Stage**: Early exploration (why/what) · Mid-design (what/how) ·
   Pre-build (implementation-ready) · Post-build (documentation)
4. **Content**: "Share whatever you have — an idea, problem statement,
   bullet points, meeting notes, anything. Even messy is fine."

If they genuinely don't know their spec type, ask: "Is this more about why
you're building something, what you're building, or how it should work?"
That maps to: early → Feature PRD, mid → Design doc, pre-build → RFC or
technical spec.

---

## Phase 2: Structure Discovery

This is the core differentiator. Instead of describing format options in
words, generate 3 concrete skeleton previews and let the user pick visually.

### Step 2.1: Generate 3 Skeletons — STOP AND WAIT FOR PICK

Based on their answers, generate 3 distinct skeleton previews in the same
response. Keep each to 15-25 lines — just headers plus a one-sentence
description of what goes in each section. Label them A, B, C.

Choose the 3 most relevant archetypes from the table in
references/spec-types.md. Make the skeletons genuinely different — don't
show three variations of the same shape. The user should feel immediate
recognition ("oh, that one") when they see the right one.

IMPORTANT: After showing the 3 skeletons, stop. Do not generate the full
spec yet. Wait for the user to pick A, B, C, or a mix before proceeding.

### Step 2.2: User Picks

Ask: "Which structure fits best — A, B, or C? Or mix elements from two?"

If Mix: ask which specific sections they want to keep from each.

Only proceed to Phase 3 after receiving their answer.

---

## Phase 3: Generate the Spec

Before generating, read:
- references/spec-types.md — section-level guidance per archetype
- references/writing-guide.md — how to write each section well

### Output requirements

- Single Markdown file, clean and readable as-is
- TL;DR at the top — 3 sentences max. Start with the problem, state the solution, name the win.
- Headers as reader questions — "Why are we building this?" not "Background"
- Inline callouts for open questions: > Open question: ...
- Inline callouts for decisions made: > Decision: ...
- Placeholders for missing content: <!-- TODO: ... -->
- Use plain language. If a sentence needs a glossary, rewrite it.

### Length targets

| Spec type         | Target length     |
|-------------------|-------------------|
| One-pager brief   | 300-600 words     |
| Feature PRD       | 600-1,200 words   |
| Technical RFC     | 800-2,000 words   |
| Architecture doc  | 1,000-2,500 words |
| Decision record   | 200-500 words     |

---

## Phase 4: Ship Readiness Check (Optional)

After generating, offer: "Want me to run a quick ship-readiness check?"

If yes, read references/ship-checklist.md and flag any gaps as a short list.

---

## Supporting Files

| File | Purpose | When to read |
|------|---------|--------------|
| references/spec-types.md | Archetype table + section guidance per type | Phase 2-3 |
| references/writing-guide.md | How to write each section well | Phase 3 |
| references/ship-checklist.md | Common gaps before sharing | Phase 4 |

---

## What Makes a Great Spec

A spec gets read when it respects the reader's time. The goal isn't
completeness — it's clarity at the right level of detail for the current stage.

The single most common mistake: writing a pre-build spec before the team
has agreed on the why. Lock the problem first. Lock the solution shape
second. Lock implementation last.

If you find yourself writing more than 3 sentences about implementation
in a PRD, you're probably in the wrong phase.
