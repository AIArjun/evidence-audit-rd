# Product Decisions

A running log of product and technical decisions for the Evidence Audit MVP. Lightweight by design: each entry captures what was decided, why, and the trade-off. Append new decisions; don't rewrite old ones — if a decision changes, add a new entry that supersedes it.

Status values: **Accepted**, **Proposed**, **Superseded**.

---

## D1 — Take the hackathon prototype into a product MVP
- **Date:** 2026-06-15
- **Status:** Accepted
- **Context:** Evidence Audit proved an architecture pattern at the hackathon but has no runnable code. The pattern — generate, extract claims, verify, report — is worth building into something usable.
- **Decision:** Start a structured product MVP build, beginning on this branch.
- **Consequences:** Work moves from documentation-only to building. Scope must stay honest about prototype origins (see D2).

## D2 — Keep the honest positioning
- **Date:** 2026-06-15
- **Status:** Accepted
- **Context:** The existing docs are deliberately honest: this is not production, it does not "solve hallucination," and it depends on retrieval quality.
- **Decision:** Carry that framing into the MVP — no overclaiming in code, docs, or demos.
- **Consequences:** Marketing-style claims stay out. Limitations stay documented as the product grows.

## D3 — Run the build on a visible control layer
- **Date:** 2026-06-15
- **Status:** Accepted
- **Context:** A solo MVP build benefits from a lightweight, inspectable process.
- **Decision:** Track the build with four documents: `BUILD_LOG.md`, `docs/day-1-plan.md`, `docs/product-decisions.md`, `docs/learning-notes.md`.
- **Consequences:** Small per-step overhead to keep these current, in exchange for a traceable build history.

## D4 — MVP target: narrow local slice first
- **Date:** 2026-06-16 — Day 1 continued
- **Status:** Accepted
- **Context:** The standalone API (future-work #1) is the long-term target, but building it first risks investing in plumbing before the audit logic is proven.
- **Decision:** Build a narrow local slice first, not a standalone API. Slice: one pasted AI answer → 3–5 extracted claims → checked against small trusted-source fixtures → one Markdown/JSON trust report, using four first-class verdicts (SUPPORTED / PARTIALLY SUPPORTED / UNSUPPORTED / CONTRADICTED). See `docs/step-0-slice.md`.
- **Consequences:** Fastest path to a working verification core. API, retrieval, and UI are deferred. `CONTRADICTED` is preserved as a distinct verdict (never merged into `UNSUPPORTED`), since a contradicted claim is known-wrong, not merely unverified.

## D5 — Stack: Python local pipeline first, FastAPI later
- **Date:** 2026-06-16 — Day 1 continued
- **Status:** Accepted
- **Context:** Future work names FastAPI, but a service wrapper adds no value until the audit logic works.
- **Decision:** Implement the slice as a Python local pipeline first; add FastAPI only after the audit logic works.
- **Consequences:** No web framework, server, or endpoints yet. Logic runs from the command line / a script.

## D6 — Source data: curated safe fixtures, no licensed passages
- **Date:** 2026-06-16 — Day 1 continued
- **Status:** Accepted
- **Context:** The audit needs evidence to check against, but licensed publisher passages cannot be reproduced here (`docs/limitations.md`).
- **Decision:** Use manually curated safe source fixtures — paraphrased source cards or clearly open-access / public-domain text. Do not reproduce licensed publisher passages.
- **Consequences:** Fixtures are safe to commit. Audit results on fixtures are illustrative, not a benchmark.

---

## Pending (awaiting input)
- _None. The Day 1 open questions (MVP target, stack, source data) are resolved by D4–D6 above._
