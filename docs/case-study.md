# Case Study: Evidence Audit — Trust Layer for AI-Assisted R&D

## Overview

At the Aris Machina × Redpine hackathon in Stockholm (May 26, 2026), I built Evidence Audit — a workflow that audits AI-generated R&D claims against licensed scientific sources. Each claim is marked SUPPORTED, PARTIALLY SUPPORTED, or UNSUPPORTED, giving the engineer a structured trust report before they act on the AI's answer. Built solo in approximately four hours using Protos, Redpine's licensed data layer, and Claude/Co-engineer reasoning.

## Problem

When an R&D engineer asks an AI assistant a technical question, the AI returns a confident, well-structured answer. But in industrial R&D, a wrong number or incorrect mechanism can lead to failed experiments, mis-designed prototypes, or unsafe decisions. The engineer's real question is not "what does the AI say?" — it is "which parts of this answer are actually grounded in the scientific literature?" Manually tracing every claim back to source papers takes hours and defeats the purpose of using AI.

## Why this matters

AI adoption in R&D is growing, but trust in AI outputs remains the bottleneck. The gap between "AI can generate an answer" and "an engineer can safely act on that answer" is where verification matters. Without a trust layer, AI-assisted R&D risks compounding errors: a hallucinated claim becomes an assumption, becomes a model input, becomes a failed prototype.

## What I built

A 7-node workflow inside Protos that takes an R&D question, retrieves relevant scientific evidence from Redpine's licensed data, generates a technical answer, extracts individual claims, audits each claim against the retrieved source passages, and produces a structured trust report with an R&D decision dashboard.

## Workflow

1. **R&D Question** — engineer asks a technical question
2. **Redpine Retrieval** — licensed scientific papers searched via Redpine's data layer
3. **Co-Engineer Answer** — Claude/Co-engineer generates a technical answer grounded in retrieved sources
4. **Claim Extraction** — each distinct technical claim is isolated
5. **Evidence Audit** — each claim is checked against source passages and labeled
6. **Trust Report** — structured output with claim, verdict, source reference, risk-if-wrong, recommended next step
7. **R&D Decision Dashboard** — visual summary with trust score and action recommendations

## Tools used

- Protos (Aris Machina) — R&D workflow workspace, Canvas, Simulation Studio
- Redpine — licensed scientific data access via MCP (Wiley, IEEE, ECS sources)
- Claude / Co-engineer — AI reasoning and claim verification

## Demo result

Question: "What are the common degradation mechanisms for lithium-ion battery cells at elevated temperatures?"

Five claims were extracted from the AI answer and audited against three Redpine sources. Three were supported, one partially supported, one unsupported. Trust score: 70%.

## Key insight

The most valuable moment was Claim 5. The Co-engineer confidently stated that lithium plating is a significant high-temperature degradation mechanism. The retrieved sources contradicted this — lithium plating is primarily a low-temperature phenomenon. Without the audit, this incorrect claim could enter a degradation model unchecked. This is the exact failure mode Evidence Audit is designed to catch: a plausible-sounding but unsupported claim that passes through if nobody verifies it.

## Why it generalizes beyond batteries

The pattern — generate AI output, extract claims, verify against trusted sources, produce structured verdicts — is not limited to battery R&D. It applies to any domain where AI-generated content must be verified before action: pharmaceutical research, regulatory compliance, technical documentation, financial analysis, legal due diligence. The architecture is domain-agnostic.

## What I would improve next

- Per-claim confidence scoring using semantic similarity between claim and source passage
- Multi-domain evidence pools beyond battery science
- A human-in-the-loop layer where the engineer can confirm, override, or annotate verdicts
- A standalone API version with FastAPI for integration into existing R&D tools
- Automated regression testing to track audit quality over time

## Closing

Evidence Audit was built in four hours as a hackathon prototype. It is not a production system. But it demonstrates a pattern I believe matters: AI should not just generate answers — it should verify them before anyone acts. This is the kind of applied AI workflow I build through arjunworks.
