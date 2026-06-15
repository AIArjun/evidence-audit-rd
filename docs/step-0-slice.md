# Step 0 — Smallest End-to-End Audit Slice

- **Date:** 2026-06-16 — Day 1 continued
- **Branch:** `product-mvp/day-1-step-0-slice`
- **Phase:** Product MVP — Day 1, Step 0
- **Status:** Specification only — no application code in this step.

## Purpose

Before writing any product code, define the smallest slice that exercises the
Evidence Audit pattern end to end. The slice is the unit we build first: small
enough to finish, complete enough to prove the verification layer works.

## The slice

One pasted AI answer → 3–5 extracted claims → each claim checked against a small
set of trusted-source fixtures → one trust report (Markdown and/or JSON).

```
Pasted AI answer (manual input)
        │
        ▼
Claim extraction        → 3–5 atomic claims
        │
        ▼
Evidence audit          → each claim vs. local source fixtures
        │                  verdict: SUPPORTED / PARTIALLY SUPPORTED /
        │                           UNSUPPORTED / CONTRADICTED
        ▼
Trust report            → Markdown and/or JSON
```

## Mapping to the 7-node architecture

The slice deliberately runs only the verification core of `docs/architecture.md`:

| Node | In the slice? | How |
|------|---------------|-----|
| 1 — R&D Question | No | Out of scope for the slice |
| 2 — Redpine Retrieval | Replaced | Local curated source fixtures stand in for live retrieval |
| 3 — Co-Engineer Answer | Manual | The AI answer is pasted in, not generated |
| 4 — Claim Extraction | Yes | Core of the slice |
| 5 — Evidence Audit | Yes | Core of the slice |
| 6 — Trust Report | Yes | Markdown / JSON output |
| 7 — Decision Dashboard | No | Later; report is text/JSON for now |

This isolates the part that matters most — checking claims against evidence —
and removes the moving parts (live retrieval, answer generation, UI) not needed
to prove it.

## Inputs and outputs

- **Input 1 — AI answer:** a short pasted technical answer (plain text).
- **Input 2 — Source fixtures:** a small local set of trusted-source cards (see below).
- **Output — Trust report:** per-claim verdict, short evidence summary, which
  fixture(s) matched, and an overall count/score. Markdown to read, JSON to reuse.

## Source-data approach (fixtures)

- Manually curated, safe source fixtures only.
- Use **paraphrased source cards** (short paraphrase + citation metadata) or
  **clearly open-access / public-domain text**.
- **Do not reproduce licensed publisher passages** (Wiley/IEEE/ECS full text,
  etc.). This matches `docs/limitations.md`.
- Each fixture carries metadata: id, title/source, year, access type
  (paraphrased | open-access), and the text used for matching.

## Verdict labels

The slice uses **four** first-class verdicts:

- **SUPPORTED** — a fixture directly backs the claim.
- **PARTIALLY SUPPORTED** — related evidence exists but doesn't fully confirm the claim.
- **UNSUPPORTED** — no fixture addresses the claim; the evidence is silent (neither backs nor opposes it).
- **CONTRADICTED** — a fixture directly opposes the claim.

**`CONTRADICTED` is kept separate from `UNSUPPORTED` and is never merged into it.**
"Unsupported" means the evidence is silent; "contradicted" means the evidence
actively disagrees. These are different signals with different risk: a
contradicted claim is a known-wrong claim, not just an unverified one. The most
valuable hackathon finding (lithium plating stated as a high-temperature
mechanism) was a *contradiction*, not an absence of evidence — so contradiction
detection stays first-class even if the first implementation is simple.

## Explicitly out of scope for the slice

- Standalone API / FastAPI service (later — see D5).
- Live Redpine retrieval / licensed-source integration.
- Frontend / dashboard.
- AI answer generation (the answer is pasted).
- Confidence scoring and an evaluation set (see `docs/future-work.md`).

## Definition of done (Step 0)

- [ ] This slice spec is recorded and agreed.
- [ ] Decisions D4–D6 recorded in `docs/product-decisions.md`.
- [ ] `BUILD_LOG.md` has a Step 0 entry.
- [ ] No product code written yet (intentional — Step 0 is design only).

_Next step (not started): turn this slice into a Python local pipeline (D5)._
