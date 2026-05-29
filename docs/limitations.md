# Limitations

This project is a hackathon prototype. It is documented honestly so that anyone evaluating it understands its scope.

- **Hackathon prototype.** Built solo in roughly four hours. It demonstrates an architecture pattern, not a finished product.
- **No production backend.** The workflow ran inside Protos during the hackathon. There is no standalone, deployable service in this repository.
- **No independent benchmark.** The audit verdicts were not validated against a labeled ground-truth dataset. The 70% trust score reflects this single demo run, not a measured accuracy figure.
- **Source passages not included.** The scientific sources were accessed through Redpine's licensed data platform. Full source passages are not reproduced in this repository. Examples use short paraphrased placeholders.
- **Audit quality depends on retrieval quality.** If retrieval misses a relevant source, a claim may be mislabeled as unsupported. The audit is only as good as the evidence it can see.
- **Verdict labels need validation for production.** The SUPPORTED / PARTIALLY SUPPORTED / UNSUPPORTED labels were assigned by AI reasoning. In production, these would need calibration and human review.
- **Single domain tested.** Only one domain (lithium-ion battery degradation) and one question were tested. Generalization to other domains is plausible but unproven.
- **Does not "solve hallucination."** It catches unsupported claims relative to the retrieved sources. It does not guarantee correctness in any absolute sense.
