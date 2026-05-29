# Future Work

Directions to take Evidence Audit from prototype toward something production-grade.

- **Production API version.** A standalone FastAPI service exposing the audit workflow as an endpoint, so it can be called from existing R&D tools rather than only inside Protos.
- **Automated evaluation set.** A labeled dataset of claims with known verdicts, to measure audit accuracy (precision/recall per verdict class) and track regressions.
- **Per-claim confidence scoring.** A numeric confidence per claim, derived from semantic similarity between the claim and its strongest supporting passage, so borderline verdicts are visible.
- **Source-contradiction detection.** Explicitly detect when sources disagree with each other, not just when a claim is unsupported. This surfaces genuine scientific disagreement.
- **Domain-specific claim extraction.** Tuned extraction for different fields (materials, pharma, semiconductors), since what counts as a "claim" varies by domain.
- **Human-in-the-loop review.** A layer where the engineer can confirm, override, or annotate each verdict, and where overrides feed back into improving the system.
- **Dashboard export.** Export the trust report to PDF or structured formats for inclusion in design reviews, reports, and audit trails.
- **Integration with existing R&D tools.** Connectors to common research and engineering workflows so the audit fits into existing processes rather than requiring a new tool.
