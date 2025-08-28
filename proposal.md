# A Proposal for Interrogatory, Low-Friction Model Cards (CAN • SHOULD • MUST)

## 1) Problem Sketch
Model cards are uneven: selective disclosure, vague provenance, flattering metrics, generic limitations. Regulation (EU AI Act) and risk frameworks (NIST AI RMF) are pushing toward evidence-backed docs, but most “cards” are still self-reported.

## 2) Design Goal
A **modern, interrogatory model card** that:
- Minimizes authoring friction
- Maximizes falsifiability/comparability
- Fits EU/NIST governance
- Works for open/closed models

**Lever:** machine-readable schema + sharp prompts + links to evidence (metrics/datasets/scripts), not essays.

## 3) CAN • SHOULD • MUST (v0.1 sketch)
**MUST**
- Identity & lineage (machine-readable)
- Intended & out-of-scope uses (≥3 concrete unsafe uses + rationale)
- Performance claims → dataset version + eval script commit + run hash (subgroup metrics if relevant)
- Limitations & failure modes (worst-case behaviors tried; at least one “worse than baseline” context)
- Data provenance summary (classes/volumes/filters; link Data Cards if possible)
- Safety testing overview (red-team/evals scope: jailbreaks, autonomy, persuasion, cyber, bio)
- Operational constraints + changelog (rate/context limits, moderation, update policy)

**SHOULD**
- One “executable” eval (small, reproducible subset)
- Map to NIST AI RMF or EU AI Act obligations
- Short System Card if shipped in a product (HITL, retention, deployment affordances)
- Bias/fairness subgroup rationale (why these; what’s missing)

**CAN**
- Third-party attestations (verify a slice of claims)
- Public card score (completeness/candor)
- Living card (auto-update + diff feed)

## 4) Low-Friction Rationale
Schema-first, link artifacts over prose, reuse compliance docs you already produce. Rough time: 4–10 hrs initial (10–20 if backfilling subgroup metrics); ~1 hr per update.

## 5) Adoption Pathways
Venues (MUST + one SHOULD), model hubs (completeness badge), procurement (map to EU/NIST), community norms (reward executable claims).

## 6) Next Steps (repo plan)
- v0.2: add JSON Schema and a minimal example card; CI to validate examples
- v0.3: sharpen interrogatory prompts; add HF-friendly README template
- v0.4: collect feedback, add third-party attestation hooks
