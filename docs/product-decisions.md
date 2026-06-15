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

---

## Pending (awaiting input)
- **MVP target** for Day 1 — standalone API vs. a narrower slice.
- **Stack** — Python/FastAPI (per future work) or alternative.
- **Source data** approach for the MVP — paraphrased placeholders vs. other.

_See `docs/day-1-plan.md` → Open questions._
