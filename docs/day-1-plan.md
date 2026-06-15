# Day 1 Plan — Control Setup & Foundation

- **Date:** 2026-06-15
- **Branch:** `product-mvp/day-1-control-setup`
- **Phase:** Product MVP — Day 1

## Where we're starting

The repository currently documents the Evidence Audit hackathon prototype: README, architecture, case study, demo script, limitations, future work, and example input/output. There is no runnable application code yet — the workflow ran inside Protos during the hackathon.

Day 1 is about putting the foundation in place to turn that documented pattern into a runnable product, without overreaching.

## Goal for Day 1

Establish the control layer (tracking docs) and agree the foundation for the MVP build, so later days can add the runnable audit pipeline against a clear, recorded plan.

## Scope

### In scope
- **Step -1 — Control setup.** Create the four tracking documents (build log, this plan, product decisions, learning notes). _(done)_
- **Step 0 — Confirm direction.** Lock the MVP target, stack, and Day 1 definition of done with the owner before writing application code. _(done — see `docs/step-0-slice.md`, D4–D6)_
- **Step 1 — Repo skeleton _(proposed)_.** Lay out structure for application code aligned with the 7-node architecture in `docs/architecture.md`.

### Out of scope for Day 1
- Full audit pipeline implementation.
- Live Redpine retrieval / licensed-source integration.
- Evaluation set, confidence scoring, and dashboard (see `docs/future-work.md`).

## Definition of done (Day 1)
- [ ] Four control documents exist and are committed.
- [x] MVP target and stack confirmed with owner and recorded in `docs/product-decisions.md`.
- [ ] Repo skeleton (if approved) committed, with the build log updated.

## Open questions (resolved in Step 0)

All three are now decided — see `docs/product-decisions.md` and `docs/step-0-slice.md`:

1. **MVP target:** ✅ Resolved — narrow local slice first, not a standalone API (D4).
2. **Stack:** ✅ Resolved — Python local pipeline first; FastAPI later (D5).
3. **Source data:** ✅ Resolved — curated safe fixtures (paraphrased source cards / open-access), no licensed passages (D6).

_This plan is a proposal. Step 0 (slice definition) is complete — see `docs/step-0-slice.md`; later steps remain open to revision._
