# Spec Types & Structure Archetypes

## Archetype Table

Use this to select the 3 most relevant skeletons for Phase 2, based on spec
type, audience, and stage.

| Archetype | Best for | Lead with | Avoid if |
|-----------|----------|-----------|----------|
| **Problem-first** | Early PRDs, mixed audience | Problem statement | Pre-build (too vague) |
| **Requirements-first** | Pre-build, engineering-heavy | Functional requirements | Exec audience (too dense) |
| **Story-first** | User-facing features, consumer | User story / JTBD | Internal tooling, infra |
| **Decision-record** | Architecture choices, RFCs | Context + options considered | Still exploring (use problem-first) |
| **Brief** | Exec, one-pagers, early alignment | TL;DR + ask | Needs implementation detail |
| **API-contract** | Integration specs, platform work | Endpoints + schema | Non-technical audiences |

---

## Archetype Skeletons

### Problem-first PRD

Best when: you have a clear user problem, mixed audience, early-to-mid stage.

```
## TL;DR
What we're building and why, in 3 sentences. Start with the problem.

## Why now?
What's changed? Why is this worth doing in this cycle vs. a later one?

## Problem
What's broken or missing. Who experiences it. How often. Evidence.

## Proposal
What we're building. Enough to understand the shape, not a wireframe spec.

## User stories
3-6 stories. Format: "When [situation], I want to [do X] so that [outcome]."

## Out of scope (v1)
Explicit list of things we're NOT doing in this version.

## Design considerations
Open UX questions, known constraints. Delete if engineering-only.

## Open questions
Unresolved things. Format: question, owner, date added.

## Success metrics
How we'll know this worked. Observable, not aspirational.

## Dependencies
Teams, systems, or decisions this work depends on.
```

---

### Requirements-first (Pre-build Spec)

Best when: the team has aligned on what, now you need to specify how clearly enough to build.

```
## TL;DR
One paragraph. What are we building and what does "done" look like?

## Context
Brief recap of why this was decided. Link to upstream PRD.

## Functional requirements
Numbered list. "The system shall..." or "Users must be able to..."

## Non-functional requirements
Performance, reliability, security, accessibility targets.

## Technical approach
High-level design decisions already made. Key tradeoffs accepted.

## Data model changes
New tables, schema changes, migration notes.

## API contract
Endpoints, request/response shape, auth.

## Edge cases & error states
Known edge cases and how they should behave.

## Testing requirements
What needs to be tested, by whom, before shipping.

## Out of scope
What we're explicitly not building in this phase.

## Open questions
Unresolved technical decisions. Owner + deadline.
```

---

### Story-first (User Experience Spec)

Best when: user-facing feature, design-heavy, the experience is the product.

```
## TL;DR
The story of what changes for the user, in 2-3 sentences.

## The problem we're solving
A short user story or scenario. One real user, one real situation.

## The experience we're designing
Walk through the intended experience as a narrative. Before / During / After.

## Jobs to be done
What are users hiring this feature to do? 2-4 JTBD statements.

## Success looks like
What changed for the user. Behavioral indicators, not metrics.

## Design principles for this feature
2-4 principles specific to this feature's UX.

## Flows to design
List the distinct flows/screens. Not specs — just the scope.

## Edge cases that affect UX
Error states, empty states, loading states, permission edge cases.

## Out of scope (this version)
What users won't be able to do yet.

## Open questions for design
Unresolved UX decisions that need input before building.
```

---

### Decision Record (ADR/RFC)

Best when: you made a significant architectural or product decision and need
to document the reasoning for future teammates.

```
## Context
What situation forced this decision? What constraints applied?

## Decision
The decision, stated plainly. One sentence if possible.

## Options we considered

### Option A — [name]
What it is. Pros. Cons.

### Option B — [name]
What it is. Pros. Cons.

### Option C — [name] (chosen)
What it is. Why we chose it. What it solves. What it costs us.

## Consequences
What gets easier. What gets harder. What this forecloses.

## Follow-up actions
Things that need to happen as a result of this decision.

## Status
Proposed / Accepted / Deprecated / Superseded by [link]
```

---

### Executive Brief (One-Pager)

Best when: you need alignment from leadership or a decision-maker.

```
## The ask
One sentence. What are you asking for?

## The opportunity
What's the opportunity or problem? Why does it matter to the business?

## The proposed approach
What we want to do. No implementation detail — just the shape.

## Why now
What's the forcing function? What happens if we wait?

## What it takes
Resources, time, rough cost. Honest about uncertainty.

## What success looks like
The outcome, 6-12 months from now, if this works.

## What we're NOT doing
One or two explicit non-goals.

## The ask (again)
Restate the specific decision or resource you need.
```

---

### API / Integration Contract

Best when: you're designing or documenting an interface between systems or teams.

```
## Overview
What does this API/integration do? Who consumes it?

## Authentication
Auth method, token type, scopes required.

## Base URL & versioning
Base URL. Versioning strategy. Deprecation policy.

## Endpoints

### [METHOD] /path/to/endpoint
Purpose: What this does.
Request: Headers, params, request body schema.
Response: Success shape + status codes.
Errors: Error codes this endpoint can return.

## Rate limits
Limits, throttling behavior, retry guidance.

## Webhooks (if applicable)
Events, payload shape, retry policy, security.

## Changelog
Breaking changes, with version and date.

## Open questions
Unresolved design decisions that affect the contract.
```
