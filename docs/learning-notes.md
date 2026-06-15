# Learning Notes

Running notes from building the Evidence Audit MVP — things learned, things that surprised me, and decisions I'd reconsider. Informal and chronological. This is for capturing insight, not polished writing.

---

## 2026-06-15 — Day 1, control setup

- Starting from a documentation-only repo. The hard part of the hackathon was the verification *layer*, not generating the AI answer — that's the part worth productizing first.
- The most valuable demo moment (Claim 5, lithium plating) came from a claim the sources *contradicted*, not one with no evidence at all. Note for the MVP: "unsupported" and "contradicted" may deserve to be distinct signals, not one bucket. (Already tracked in `docs/future-work.md` as source-contradiction detection.)
- Set up the control layer before any code, to keep a solo build honest and traceable.

_Add notes as the build progresses._
