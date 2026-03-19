# Writing Guide: How to Write Each Section Well

## Universal rules

**The TL;DR is the most important section.** Write it last. It should compress
the whole spec into 3 sentences: (1) what we're building, (2) why, (3) what
winning looks like. If you can't write this, the spec isn't ready.

**Headers are promises.** "Background" promises nothing. "Why we're building
this now" promises an argument. Make the promise, then fulfill it.

**The reader is busy and slightly skeptical.** Write for someone who will skim
the headers, read the TL;DR, and only go deeper if they're not satisfied.

**Kill weasel words.** Replace with observable outcomes:
- "Improve onboarding" → "Reduce time-to-first-value from 3 days to 1"
- "Enhance search" → "Surface relevant results in <200ms"
- "Better error handling" → "Every error state has a recovery path"

---

## Section-by-section guidance

### TL;DR
Compress the whole spec into 3 sentences:
1. What we're building (noun, not a verb-heavy description)
2. Why it matters now (the forcing function or opportunity)
3. What success looks like (observable, not aspirational)

Write this last. If you write it first, it becomes a mission statement.

**Weak:** "We are working on improving our export functionality to provide users with better options."

**Strong:** "We're adding CSV export to the dashboard so users can pull their data into their own tools. Without it, 3 of our top 5 enterprise deals are blocked. Done means: one click from any table view, under 3 seconds for up to 50k rows."

---

### Problem
The single most important section in any early-stage spec. A good problem
statement answers:
- **Who** has this problem? (A specific persona, not "users")
- **What** are they trying to do? (The job, not the feature)
- **Why** can't they do it today? (The gap, the friction, the cost)
- **How do we know?** (Evidence: support tickets, data, quotes, interviews)

**Weak:** "Users have been asking for CSV export."

**Strong:** "Enterprise users run weekly reports by manually copy-pasting table data into Google Sheets — a process that takes 20-40 minutes and introduces errors. We've logged 47 support requests in the last quarter; 3 enterprise deals cited its absence as a blocker."

---

### Proposal
Describe the solution at the level of a smart, opinionated paragraph — enough
to understand the shape, not enough to debate implementation.

Include:
- What you're building and how it fits into the existing product
- Key design decisions already made

Do NOT include:
- Implementation details (that's the RFC)
- Every edge case (that's the requirements doc)
- Why this approach vs. others (that's the decision record)

---

### User Stories
Format: "When [situation/context], I want to [action/ability] so that [outcome/value]."

Rules:
- 3-6 stories max in a PRD
- Each story represents a distinct need, not a variation on the same one
- The "so that" matters — it ties the feature to user value

**Weak:** "As a user, I want to export data so I can use it."

**Strong:** "When I've filtered my dashboard to a specific date range and campaign, I want to download the result as a CSV so I can paste it into my weekly report without redoing the filtering manually."

---

### Out of Scope
This section prevents your spec review from becoming a wishlist session.

Good out-of-scope items:
- Things reviewers will definitely ask about
- Natural extensions that would balloon the scope
- Features you plan to build later (flag as "v2 consideration")

**Weak:** "Advanced features are out of scope."

**Strong:**
- Custom delimiters (TSV, pipe-separated) — v2 consideration
- Scheduled/recurring exports — post-launch if demand confirms it
- Export from mobile — separate workstream

---

### Open Questions
Every good spec has open questions. If yours doesn't, you haven't thought hard enough.

Format each as:
- The question (specific, answerable)
- Owner (who resolves it)
- Deadline (when it blocks work)

**Weak:** "We need to figure out the design."

**Strong:**
> Open question: Should exports be synchronous or async (email delivery for large exports)?
> This affects the UX pattern significantly. Owner: @jamie + @design. Needed by: sprint kickoff.

---

### Success Metrics
Rules:
- Make them observable (someone should be able to pull a number)
- Make them directional (increase/decrease/maintain)
- 2-4 metrics is usually right
- Structure: Primary (the one number that matters), Secondary (supporting signal), Guardrail (what you're watching to not break)

**Weak:** "Users should be satisfied with the export feature."

**Strong:**
- Primary: 30% of active dashboard users export at least once in 30 days
- Secondary: Export error rate < 1%
- Guardrail: Dashboard page load time doesn't regress

---

### Dependencies
For each dependency, name:
- What you need (artifact, decision, or code)
- Who owns it
- When you need it
- What's at risk if it's late

---

### Technical Approach (pre-build specs)
A concise summary of key technical decisions made. NOT the implementation plan.

Cover:
- Technology/libraries chosen and why
- Key architectural decisions (not every decision)
- Known tradeoffs accepted

---

## Formatting rules

**Do:**
- Use `> Open question:` callouts for unresolved questions
- Use `> Decision:` callouts for things already decided
- Use `<!-- TODO: add X -->` for placeholders
- Use numbered lists for requirements (easier to reference in review)

**Don't:**
- Use passive voice in requirements ("It should be possible to...")
- Nest bullets more than 2 levels deep
- Use bold randomly
- Write more than 3-4 sentences in a single paragraph

---

## Common mistakes

**The orphaned section:** Every section should connect to the ones around it.
If your Success Metrics don't reference anything in Proposal or User Stories,
you're probably measuring the wrong thing.

**The everything-is-in-scope spec:** If your Out of Scope section is empty,
you haven't made hard calls yet.

**The implementation-in-PRD problem:** If a PRD section could only be written
by an engineer, it's in the wrong doc. Move it to the RFC.

**The committee spec:** If a spec was written by committee, you can tell — it
covers everything and commits to nothing. One person writes the spec; others review.
