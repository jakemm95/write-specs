# write-specs

A Claude skill for writing clear, shipworthy product specs — from scratch, rough notes, or existing drafts.

## What it does

`write-specs` turns blank-page anxiety and rough ideas into product specs that actually get read. It guides you through **structure discovery** — generating 3 concrete spec skeleton previews and letting you pick the shape that fits your mental model — rather than asking you to describe your format preferences in the abstract.

Works with: Feature PRDs · Technical RFCs · Design decision docs · Architecture overviews · One-pager briefs · API/integration specs

## Why it works this way

Most spec-writing tools start with a template. The problem is that the right template depends on your audience, your stage, and what kind of alignment you're after — and it's hard to know which you want until you see them side by side.

Instead of asking "what format do you prefer?", `write-specs` generates three short skeleton previews and lets you pick. People know what they like when they see it.

## How to use it

Install the skill, then in any Claude conversation say something like:

- "Write a spec for [feature idea]"
- "Turn these notes into a PRD"
- "Help me spec this RFC"
- "Write a one-pager about this project"
- "Document this architecture decision"

Claude will walk you through 4 phases:
1. **Content discovery** — 4 quick questions to understand what you're building
2. **Structure discovery** — 3 skeleton previews to pick from
3. **Generate** — full spec in your chosen structure
4. **Ship readiness check** (optional) — gaps flagged before you share

## File structure

```
write-specs/
├── SKILL.md                          # Main skill — the map
└── references/
    ├── spec-types.md                 # 6 spec archetypes with full skeletons
    ├── writing-guide.md              # Section-by-section writing guidance
    └── ship-checklist.md             # Pre-share readiness checklist
```

The `SKILL.md` is the entry point — supporting files are loaded on-demand. The main file stays lean; depth lives in the references.

## Spec types supported

| Archetype | Best for |
|-----------|----------|
| Problem-first | Early PRDs, mixed eng/PM/design audience |
| Requirements-first | Pre-build, engineering-heavy specs |
| Story-first | User-facing features, consumer products |
| Decision record | Architecture choices, RFCs |
| Executive brief | One-pagers, exec alignment |
| API contract | Integration specs, platform work |

## What makes a great spec

A spec gets read when it respects the reader's time. The goal isn't completeness — it's clarity at the right level of detail for the current stage.

- **Early-stage** → answer *why*. Lock the problem before the solution.
- **Mid-stage** → answer *what*. What are we building, not how.
- **Pre-build** → answer *how*. Detailed enough to build without a meeting.

The single most common mistake: writing a pre-build spec before the team has agreed on the *why*.

## Output format

Clean Markdown — works in Notion, Linear, GitHub, Confluence, anywhere.
