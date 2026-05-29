# Architecture

Evidence Audit is a 7-node workflow. Each node has a clear purpose, input, output, and a failure mode it is designed to prevent.

```
[1] R&D Question
        │
        ├──→ [2] Redpine Retrieval ──┐
        │                            │
        └───────────────────────────→ [3] Co-Engineer Answer
                                              │
                                              ▼
                                      [4] Claim Extraction
                                              │
                                              ▼
                                      [5] Evidence Audit
                                              │
                                              ▼
                                      [6] Trust Report
                                              │
                                              ▼
                                    [7] R&D Decision Dashboard
```

---

## Node 1 — R&D Question

- **Purpose:** Capture the technical question the engineer wants answered.
- **Input:** A natural-language R&D question.
- **Output:** A structured question passed to retrieval and reasoning.
- **Failure mode prevented:** Ambiguous or unscoped questions that produce unfocused answers.

## Node 2 — Redpine Retrieval

- **Purpose:** Retrieve relevant licensed scientific passages.
- **Input:** The R&D question.
- **Output:** A set of ranked source passages with metadata (title, publisher, year).
- **Failure mode prevented:** Answers grounded in general web knowledge rather than peer-reviewed science.

## Node 3 — Co-Engineer Answer

- **Purpose:** Generate a technical answer using the retrieved sources.
- **Input:** Question + retrieved passages.
- **Output:** A technical answer containing multiple claims.
- **Failure mode prevented:** Answers detached from the retrieved evidence.

## Node 4 — Claim Extraction

- **Purpose:** Break the answer into distinct, individually checkable claims.
- **Input:** The generated answer.
- **Output:** A numbered list of atomic technical claims.
- **Failure mode prevented:** Auditing a whole answer as one unit, which hides individual errors.

## Node 5 — Evidence Audit

- **Purpose:** Check each claim against the retrieved sources and assign a verdict.
- **Input:** Each claim + retrieved passages.
- **Output:** Per-claim verdict (SUPPORTED / PARTIALLY SUPPORTED / UNSUPPORTED) + evidence summary.
- **Failure mode prevented:** Confident but unsupported claims passing through unchecked.

## Node 6 — Trust Report

- **Purpose:** Structure the audit results into a reusable artifact.
- **Input:** All claim verdicts.
- **Output:** A structured report: claim, verdict, source reference, risk-if-wrong, recommended next step.
- **Failure mode prevented:** One-off chat answers that cannot be stored, compared, or reused.

## Node 7 — R&D Decision Dashboard

- **Purpose:** Summarize the audit for decision-making.
- **Input:** The trust report.
- **Output:** Trust score, verdict counts, and per-claim action recommendations (Safe to Use / Needs Refinement / Do Not Use).
- **Failure mode prevented:** Engineers acting on the answer without seeing which parts are trustworthy.
