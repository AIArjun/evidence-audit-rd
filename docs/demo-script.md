# Demo Script

## 3-Minute Version

**[0:00–0:20] Intro + Problem**

"Hi, I'm Arjun. I built Evidence Audit — a trust layer for AI-assisted R&D. The problem: R&D teams don't just need faster AI answers. They need answers they can trust. If an AI gives a confident but wrong degradation mechanism, an engineer builds the wrong model or runs the wrong experiment."

**[0:20–0:50] What I built**

"So I built this: Claude reasons, Redpine grounds, Protos operationalizes. The Co-engineer generates a technical answer, Redpine provides licensed scientific sources — Wiley, IEEE, ECS — and Protos captures the full audit as a traceable 7-node workflow."

**[0:50–2:15] Demo**

"I asked: what are the common degradation mechanisms for lithium-ion cells at elevated temperatures? The system audited five claims against three Redpine sources. Trust score: 70%.

Three claims supported — SEI growth, electrolyte decomposition, cathode dissolution. One partially supported — loss of active material, flagged as synergistic rather than independent.

The key finding is Claim 5. The AI said lithium plating is a significant high-temperature mechanism. Two of three sources contradict this — it's a low-temperature phenomenon. Verdict: unsupported. Without this audit, that wrong claim goes into a degradation model unchecked."

**[2:15–3:00] Closing**

"Most AI workflows stop at answer generation. I added the verification layer. The engineer gets claim, verdict, source passage, risk if wrong, and recommended next step. This is not a better chatbot — it's AI-assisted R&D decision-making. AI speed with scientific rigor."

---

## 60-Second Version

"I'm Arjun. I built Evidence Audit — a workflow that audits AI-generated R&D claims against licensed scientific sources. I tested it on lithium-ion battery degradation. The AI gave five technical claims; the system audited each against three Redpine sources. Three supported, one partial, one unsupported — the AI claimed lithium plating is a high-temperature mechanism, but the sources contradicted it. Trust score: 70%. Claude reasons, Redpine grounds, Protos operationalizes. Most AI workflows stop at generating answers. I added the verification layer."

---

## Prepared Answers

### "Why Protos, not just Claude?"

"Claude does the reasoning — that part is essential. But Protos makes the workflow visible and reusable for an R&D team. The question, sources, claims, verdicts, risks, and decisions are connected in one workspace the whole team can inspect and rerun. Claude reasons; Protos turns that reasoning into a repeatable R&D process."

### "Why Redpine?"

"The audit is only as trustworthy as the evidence it checks against. Redpine provides licensed, peer-reviewed scientific sources — not web scrapes. When the audit says 'supported by Wiley 2025,' that's a real, citable source. That's what makes the trust report defensible."

### "Why does this matter for R&D?"

"In R&D, acting on a wrong claim is expensive — failed experiments, mis-designed prototypes, wasted months. The verification layer catches unsupported claims before they become assumptions in a model. It turns AI speed into AI speed with scientific rigor."
