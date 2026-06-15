# Build Log

A chronological, append-only record of the Evidence Audit product MVP build. The hackathon prototype (May 26, 2026) proved the architecture pattern; this log tracks the work of turning it into a runnable product.

Each entry notes what was done, why, and anything that changed the plan. Append new entries — don't rewrite old ones.

---

## Day 1 — 2026-06-15

### Step -1 — Control setup

- Branched `product-mvp/day-1-control-setup` from `origin/main`.
- Created the four control documents this build runs on:
  - `BUILD_LOG.md` (this file) — chronological build record.
  - `docs/day-1-plan.md` — scope and steps for Day 1.
  - `docs/product-decisions.md` — running log of product/technical decisions.
  - `docs/learning-notes.md` — running notes of what was learned while building.
- No application code changed. This step only sets up the tracking layer.

### Step 0 — Define the smallest end-to-end slice

_2026-06-16 — Day 1 continued_

- Branched `product-mvp/day-1-step-0-slice` from `origin/main` (Step -1 merged via PR #1).
- Defined the smallest end-to-end audit slice in `docs/step-0-slice.md`: one pasted AI answer → 3–5 extracted claims → checked against small trusted-source fixtures → one Markdown/JSON trust report.
- Recorded decisions D4–D6 in `docs/product-decisions.md`: narrow local slice first (not a standalone API), Python local pipeline first (FastAPI later), and curated safe source fixtures (no licensed passages).
- Verdict scheme keeps four first-class labels — SUPPORTED / PARTIALLY SUPPORTED / UNSUPPORTED / CONTRADICTED — with `CONTRADICTED` never merged into `UNSUPPORTED`.
- Marked the Day 1 plan's open questions resolved (point to D4–D6).
- Documentation only — no product code, no Python implementation, no API/backend/frontend files.

_Next (not started): implement the slice as a Python local pipeline (D5)._
