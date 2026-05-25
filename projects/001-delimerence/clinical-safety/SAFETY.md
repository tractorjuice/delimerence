# Clinical Safety — DeLimerence

> **Template Origin**: Community | **ArcKit Version**: 5.0.6 | **Command**: `/arckit-uk-nhs:uk-nhs-dcb0129` | **Filename**: `SAFETY.md` (DCB0129 manufacturer anchor)

## Document Control

| Field | Value |
|---|---|
| **Document ID** | `SAFETY.md` (Marcus Baw SAFETY.md spec convention; no ARC- prefix) |
| **Document Type** | Clinical Safety Anchor (DCB0129 manufacturer) |
| **Project** | DeLimerence (Project 001) |
| **Classification** | OFFICIAL |
| **Status** | DRAFT |
| **Version** | 0.1 |
| **Created Date** | 2026-05-25 |
| **Last Modified** | 2026-05-25 |
| **Review Cycle** | Quarterly (recommended for active products) |
| **Next Review Date** | 2026-08-25 |
| **Owner** | Mark Craddock, Product Owner |
| **Reviewed By** | [PENDING — CSO] |
| **Approved By** | [PENDING — CSO sign-off in SAFETY-CASE.md §6] |
| **Distribution** | Clinical Advisory Board, Ethics Review Panel, DPO |

## Revision History

| Version | Date | Author | Changes | Approved By | Approval Date |
|---|---|---|---|---|---|
| 0.1 | 2026-05-25 | ArcKit AI | Initial creation from `/arckit-uk-nhs:uk-nhs-dcb0129` command | PENDING | PENDING |

---

## Applicability statement

DeLimerence is currently positioned (per ARC-001-REQ-v1.0 NFR-C-003) as a **psychoeducation and self-help tool, not a medical device**, and is not being placed into NHS service. NHS DCB0129 is mandated for health IT placed into NHS service under the Health and Social Care Act 2012 s250. The strict regulatory applicability of DCB0129 to DeLimerence is therefore **conditional**:

- If the product is referred to or distributed by NHS services, or accepts NHS-funded users via a contracted pathway → DCB0129 applies in full and a DCB0160 deployer case is required from each deploying NHS organisation.
- If MHRA classification (per BR-004) determines DeLimerence is a medical device → ISO 14971 risk management file is mandatory under UK MDR 2002; DCB0129 applies if NHS-deployed.
- If positioning remains "general public adult self-help, no NHS pathway" → DCB0129 is **precautionary** and this safety case operates as a voluntary best-practice clinical safety artefact for Clinical Advisory Board sign-off.

This document is generated as a precautionary safety case. It does not replace MHRA pre-submission engagement (BR-004), the DPIA (ARC-001-DPIA-v1.0), or Clinical Advisory Board protocol sign-off. The CSO appointed for DeLimerence MUST review the applicability question above and adjust the document set accordingly.

---

## Required SAFETY.md fields (Marcus Baw SAFETY.md spec v2.0.0)

| Field | Value |
|---|---|
| `product-name` | DeLimerence |
| `version` | 0.1 (pre-beta) |
| `standard` | DCB0129 (precautionary — see Applicability above) |
| `clinical-safety-officer` | [PENDING — CSO name and GMC/NMC/HCPC/GPhC registration number to be appointed by the Clinical Advisory Board before public beta] |
| `organisation` | DeLimerence (legal entity to be confirmed at incorporation — see ARC-001-RISK-v1.0) |
| `safety-case-status` | draft |
| `hazard-log-url` | [./HAZARD-LOG.md](./HAZARD-LOG.md) |
| `last-reviewed` | 2026-05-25 |

---

## Summary

DeLimerence is an anti-dependency conversational AI tool for limerence recovery. It is the deliberate inversion of AI companion apps — designed to loosen attachment rather than deepen it — and operationalises the CBT/ERP framework adapted from OCD protocols (Wyant, 2021) in a 24/7 conversational format. Users are adults experiencing limerence, a state of involuntary neurochemical obsessive attachment characterised by intrusive thoughts (typically 2–8 hours daily), compulsive checking rituals, and acute distress concentrated in out-of-hours periods. The intended scope of this safety case is **Phase 1 only — psychoeducation, ritual tracking, and structural anti-dependency constraints**; Phase 2 (CBT/ERP intervention) is excluded pending MHRA classification clarity.

The safety approach combines (a) **structural anti-dependency constraints** enforced server-side (20-exchange session cap, 8-hour cooldown, "Tool" persona, anti-warmth system prompt, action commitment gate), (b) a **multi-layer LLM safety stack** (NeMo Guardrails plus a custom clinical-warmth/diagnostic filter applied to every model response before delivery), (c) **crisis detection and handoff** to Samaritans / 999, and (d) **graduated intervention** prompting therapist involvement at session 10+. The defining existential clinical hazard — that a tool designed to counter limerent attachment instead becomes a new object of limerent attachment — is treated as the top safety claim in the Clinical Safety Case Report.

---

## Documents

- [Clinical Safety Case Report](./SAFETY-CASE.md) — the substantive safety argument
- [Hazard Log](./HAZARD-LOG.md) — the YAML-frontmatter hazard register with rendered table
- [Clinical Risk Management Plan](./SAFETY-PLAN.md) — *(not generated; consider adding under Tier 3 if MHRA classifies DeLimerence as SaMD)*

---

## Tier

This product is assessed as Marcus Baw SAFETY.md **Tier 2** by default (3-file set). Move to **Tier 3** (add `SAFETY-PLAN.md`) if MHRA determines DeLimerence is software-as-a-medical-device, in which case an explicit Clinical Risk Management Plan will be required for the Notified Body / MHRA submission.

---

## Important

This document is **not** clinical, legal, or regulatory advice. It is a generated starting point that MUST be reviewed, materially supplemented, and signed off by a qualified Clinical Safety Officer (CSO) holding current GMC / NMC / HCPC / GPhC registration before the product is placed into clinical use or referred to by NHS or other regulated clinical services.

The hazards in [HAZARD-LOG.md](./HAZARD-LOG.md) are a **starter set tailored to DeLimerence's anti-dependency architecture and clinical context**. A proper hazard identification workshop with the Clinical Advisory Board will likely add a further 20–40 hazards. A short hazard log is more often a sign of insufficient analysis than of a safe product.

---

**Generated by**: ArcKit `/arckit-uk-nhs:uk-nhs-dcb0129` command
**Generated on**: 2026-05-25
**ArcKit Version**: 5.0.6
**Project**: DeLimerence
**Model**: claude-opus-4-7[1m]
**Spec lineage**: [Marcus Baw SAFETY.md v2.0.0-draft](https://github.com/pacharanero/SAFETY.md)
