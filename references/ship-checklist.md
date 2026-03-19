# Ship Readiness Checklist

Use this in Phase 4 to audit a spec before it goes to reviewers or
gets handed to the build team. Read the spec, check each item, and
surface any gaps as a short list.

Output format: Don't score the spec. Don't produce a report.
Just say: "Before you share this, you might want to add: [x], [y], [z]."
If everything looks good, say so.

---

## Clarity checks

- [ ] TL;DR exists and covers: what we're building, why now, what success looks like
- [ ] The problem is specific — "users are confused" is not a problem; a real problem names who, what, and has evidence
- [ ] No weasel words in the proposal or success metrics ("improve," "enhance," "better," "optimize" without observable outcomes)
- [ ] Every acronym and internal term is defined on first use

---

## Completeness checks by type

### All spec types
- [ ] TL;DR
- [ ] Clear statement of what's in scope
- [ ] Clear statement of what's out of scope

### Feature PRD
- [ ] Problem statement with evidence (not just assertion)
- [ ] Proposal that explains the shape without prescribing implementation
- [ ] User stories that cover the core flows
- [ ] Success metrics (primary + at least one guardrail)
- [ ] Open questions documented (or section explicitly marked "none")

### Technical RFC / Architecture Doc
- [ ] Context section explaining why this decision was needed
- [ ] At least 2 options considered (including status quo)
- [ ] Clear statement of the chosen approach and why
- [ ] Consequences/tradeoffs acknowledged
- [ ] Dependencies identified

### Pre-build Spec
- [ ] Functional requirements are numbered and testable
- [ ] Edge cases and error states are documented
- [ ] API contract or data model changes are specified
- [ ] Testing requirements are named

### Executive Brief
- [ ] The ask is explicit (decision, resource, direction)
- [ ] The ask appears both at the top and bottom
- [ ] "Why now" is answered — what's the forcing function?
- [ ] What it takes is honest about uncertainty

---

## Collaboration readiness checks

- [ ] Open questions have owners and deadlines — "TBD" is not an owner
- [ ] All TODOs are either filled in or explicitly flagged for the reader
- [ ] Dependencies are named and those teams know before the spec goes out
- [ ] Reviewers know what you want from them — add a note: "Please review by [date]. Looking for: [specific feedback]."

---

## Stage-appropriateness check

- **Early-stage spec?** Should answer why clearly, not how. If more than 20% is implementation detail, it's probably mis-staged.
- **Pre-build spec?** Should be detailed enough that an engineer who wasn't in any design meetings could start building.
- **Post-build doc?** Should be written for someone maintaining this system 2 years from now with no prior context.

---

## Common gaps by spec type

**PRDs most commonly missing:**
- Evidence for the problem (data, quotes, support tickets)
- Explicit out-of-scope items (reviewers will ask)
- Guardrail metrics (what you're watching to not break)

**RFCs most commonly missing:**
- Status quo as an option considered
- Explicit consequences/tradeoffs of the chosen approach
- Follow-up actions that result from the decision

**Pre-build specs most commonly missing:**
- Error states and empty states
- Edge cases that affect the data model
- Non-functional requirements (performance, reliability)

**One-pagers most commonly missing:**
- The explicit ask (what decision do you need?)
- Why now (what changes if we wait 3 months?)
- Honest scope of what it takes
