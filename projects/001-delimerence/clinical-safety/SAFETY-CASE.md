# Clinical Safety Case Report — DeLimerence

> **Template Origin**: Community | **ArcKit Version**: 5.0.6 | **Command**: `/arckit-uk-nhs:uk-nhs-dcb0129` | **Filename**: `SAFETY-CASE.md` (DCB0129 manufacturer case)

## Document Control

| Field | Value |
|---|---|
| **Document ID** | `SAFETY-CASE.md` (Marcus Baw SAFETY.md spec convention; no ARC- prefix) |
| **Document Type** | Clinical Safety Case Report (DCB0129 manufacturer) |
| **Project** | DeLimerence (Project 001) |
| **Classification** | OFFICIAL-SENSITIVE |
| **Status** | DRAFT |
| **Version** | 0.1 |
| **Created Date** | 2026-05-25 |
| **Last Modified** | 2026-05-25 |
| **Review Cycle** | Quarterly (recommended); on every material product change |
| **Next Review Date** | 2026-08-25 |
| **Owner** | Mark Craddock, Product Owner |
| **Reviewed By** | [PENDING — CSO] |
| **Approved By** | [PENDING — CSO sign-off in §6 below] |
| **Distribution** | Clinical Advisory Board, Ethics Review Panel, DPO, Funders (under NDA) |

## Revision History

| Version | Date | Author | Changes | Approved By | Approval Date |
|---|---|---|---|---|---|
| 0.1 | 2026-05-25 | ArcKit AI | Initial creation from `/arckit-uk-nhs:uk-nhs-dcb0129` command | PENDING | PENDING |

---

## Risk scoring scales (DCB0129 convention)

| Scale | 1 | 2 | 3 | 4 | 5 |
|---|---|---|---|---|---|
| **Severity** | Catastrophic | Major | Considerable | Significant | Minor |
| **Likelihood** | Very High | High | Medium | Low | Very Low |

**Risk levels**: `unacceptable` · `high` · `medium` · `low`
**Hazard status**: `open` · `mitigated` · `accepted` · `closed`

> ⚠️ DCB0129 inverts the usual Orange Book convention where 5 = highest. Read carefully when cross-referencing `ARC-001-RISK-v1.0.md`.

---

## 1. Intended Use

### What this product is

DeLimerence is a conversational AI tool that helps adults experiencing limerence — an involuntary neurochemical state of obsessive attachment — to recognise their condition, track their limerent rituals, reduce ritual frequency, and engage with psychoeducation about the underlying mechanisms. It is delivered as a 24/7 web and mobile PWA, intended for moments of acute distress (typically out-of-hours) when professional support is not accessible. The intended scope of this safety case is **Phase 1 only — psychoeducation, ritual tracking, and structural anti-dependency constraints**. Phase 2 (CBT/ERP intervention protocols adapted from Wyant, 2021) is out of scope pending MHRA classification clarity (per ARC-001-REQ-v1.0 NFR-C-003 and the phased-launch decision in `decisions/`).

### What this product is not

- Not a medical device (current MHRA positioning per NFR-C-003 — to be confirmed by written determination before public beta)
- Not a diagnostic tool — does not diagnose limerence, OCD, depression, anxiety, or any clinical condition
- Not a replacement for therapy, GP consultation, or crisis services
- Not a companion app — explicitly anti-dependency, designed to loosen attachment, not deepen it
- Not for under-18s — adult-only (BR-001 Out of Scope; FR-010 age verification)
- Not for users in acute crisis — handoff to Samaritans/999 is the safe behaviour (UC-4)
- Not for users with severe co-morbid mental illness requiring clinical care (NHS Talking Therapies signposting per C019)
- Not a research instrument that publishes individual-level data (anonymised aggregate only, opt-in)

### Intended users

Adults (18+) experiencing limerence at the initiation, crystallisation, deterioration, or resolution phase of the limerence trajectory. Specifically:

- *Persona 1 — The Acute Limerent*: in active limerence, intrusive thoughts 2–8 hours daily, accessing the tool at moments of acute distress.
- *Persona 2 — The Recovery Seeker*: aware of their limerence, seeking structured recovery, with or without access to therapy.
- *Persona 3 — The Therapist Partner*: mental-health professional whose client uses DeLimerence between sessions (interacts with anonymised tracking data only, not the conversational interface).

### Intended patient population

Note: "Patient" framing is itself out of step with the product's positioning. DeLimerence does not have patients — it has adult self-help users. The DCB0129 convention is preserved in this section for compatibility but the substantive term throughout this document is **user**.

Adult general population (18+) self-identifying as experiencing limerence. Explicitly excluded: minors, users in acute suicidal crisis (handoff per C006), users with severe co-morbid mental illness for whom self-help tools are clinically inappropriate (C019).

### Intended clinical context

Self-administered use; no clinical setting required. Designed for the home / personal-device context, typically out-of-hours when professional support is unavailable. May be used alongside professional therapy (BR-005) but is not delivered through a clinical pathway and does not require referral or prescription.

---

## 2. Scope

### In scope for this safety case

- The Phase 1 product as defined in ARC-001-REQ-v1.0: conversational AI with anti-dependency architecture, ritual tracking, psychoeducation delivery engine, action commitment gate, crisis detection and handoff, graduated therapist-involvement prompts.
- The 9 structural anti-dependency constraints (session limits, cooldown, no persona, anti-warmth prompt, action commitment, graduated intervention, phase-aware responses, ritual tracking, psychoeducation in context).
- The multi-layer LLM safety stack (NeMo Guardrails + custom clinical-warmth/diagnostic filter per NFR-SEC-006).
- Authentication and consent flow (FR-010) including age gate.
- Data handling for session transcripts, ritual data, phase data, and self-assessment scores.
- LLM provider integration: Anthropic Claude via AWS Bedrock, eu-west-2 (UK data residency).

### Out of scope for this safety case

- Phase 2 CBT/ERP intervention protocols — separate safety case once MHRA classification confirms scope.
- Detection tools for platform operators (separate dual-use defensive project per ARC-001-REQ-v1.0).
- Law enforcement training materials.
- Integration with electronic health records (BR-001 Out of Scope).
- Treatment of conditions other than limerence.
- Support for minors (separate product would be required, with separate safeguarding architecture).
- Deployment-side hazards owned by any organisation that elects to refer users to DeLimerence (e.g., an NHS Talking Therapies service offering DeLimerence between sessions). These would require a DCB0160 deployer case from that organisation (`/arckit-uk-nhs:uk-nhs-dcb0160`).

### Deployment assumptions

The manufacturer assumes that:

- Users access the product directly via web or mobile PWA, not through an NHS clinical pathway.
- The deploying environment is the user's own device and network — not a clinical workstation.
- No clinical staff use the product on behalf of a user.
- No NHS Spine, NHS Number, or other NHS infrastructure integration exists.
- The hosting infrastructure (AWS eu-west-2) meets UK GDPR data residency and NHS data security standards (referenced for ambient compliance posture even though not NHS-deployed).
- Users self-declare adulthood and accept the consent flow free of coercion.

If any of these assumptions cease to hold (e.g., a partner NHS Trust starts referring users), a DCB0160 deployer case is required from that organisation and additional manufacturer-side hazards must be opened.

---

## 3. Safety Argument

Top-level claim:

> **G1: DeLimerence is acceptably safe for use by adults (18+) self-identifying as experiencing limerence, when used in the home / personal-device context as intended, with the structural anti-dependency architecture and multi-layer safety stack in place.**

This claim is supported by the sub-claims below. Each sub-claim references hazards (H-ID) from the [Hazard Log](./HAZARD-LOG.md) and the controls (C-ID) that mitigate them.

### G1.1 — The defining product hazard (limerence transfer to the tool) is systematically constrained

The existential product hazard (per BR-002 and H001) is that a tool designed to counter limerent attachment becomes itself a new object of limerent attachment. This is treated as the **top safety claim** for DeLimerence — not a peripheral hazard.

Evidence:

- Five structural controls are stacked against H001 — C001 (session limit), C002 (cooldown), C003 (no persona), C004 (action commitment gate), C005 (transparency reminders).
- Each control is enforced server-side and is non-bypassable from the client.
- Cooldown compliance rate is a defined operational metric (NFR-M-002) with alerting on circumvention attempts.
- BR-002 success criteria — "zero reported cases of limerence transfer to the tool within first year of operation" and "declining average session frequency per user over time" — are tracked and reported to the Clinical Advisory Board annually.
- Residual risk on H001 remains **HIGH** after controls (severity 1 / likelihood 4 → high). Acceptance rationale is captured in §5.

### G1.2 — Crisis events are handed off to appropriate human / statutory services

The product's safe behaviour at the moment of crisis is **not to attempt therapy** but to hand off to Samaritans, SHOUT, or 999 (UC-4).

Evidence:

- C006 — crisis detection runs on every user message and takes priority over session termination, cooldown, and LLM availability.
- C007 — pattern set reviewed quarterly with CAB; adversarial red-team test set monitored for false-negative rate.
- C008 — graduated intervention prompts therapist involvement at session 10+.
- C023 — static-content fallback under LLM outage routes crisis patterns first.
- Residual risk on H002 remains **HIGH** (severity 1 / likelihood 4) — see §5.

### G1.3 — The product does not make diagnostic claims and remains on the non-medical-device positioning

Sustaining the non-medical-device positioning (NFR-C-003) is a clinical-safety claim as well as a regulatory one: a tool that drifts into diagnostic register exposes users to harm from self-treatment based on AI-generated "diagnoses".

Evidence:

- C010 — multi-layer LLM safety stack (NeMo Guardrails + custom diagnostic filter) inspects every response before delivery.
- C011 — diagnostic-language pattern set explicitly blocks "you have", "you are suffering from", "this is the diagnosis of" and similar.
- C012 — phase assessment framed to the user as "response calibration", not as diagnosis; UX wording reviewed by CAB.
- C015 — psychoeducation content library curated and CAB-approved; LLM-generated neuroscience claims grounded to a citation set.
- C016 — behavioural advice patterns ('go no-contact', 'block them') redirected to 'discuss with a therapist' framing.
- Mitigates H004 (diagnostic over-claim) and H006 (LLM hallucination).

### G1.4 — Phase-appropriate intervention strategies prevent harm from mis-targeted interventions

A user in deterioration / grief subjected to reality-testing experiences invalidation; the same user in crystallisation appropriately requires reality-testing. Phase mis-assessment is a clinical-safety hazard, not just a UX hazard.

Evidence:

- C013 — phase reassessment triggered on conversational signal shift; inconclusive reassessment defaults to least-harmful psychoeducation-only mode.
- C014 — per-phase intervention strategies CAB-signed-off and branch-tested.
- Mitigates H005 (phase misassessment).

### G1.5 — Anti-warmth conversational behaviour is preserved as a safety property, not a stylistic choice

Companion-coded warmth language is a direct contributor to H001 (limerence transfer). Anti-warmth is treated as a safety-critical property of the system prompt, not a tonal preference.

Evidence:

- C009 — anti-warmth system prompt is version-controlled (NFR-M-001) and CAB-approved on every material change; 15-minute rollback capability.
- C010 — every model response inspected by NeMo Guardrails + custom clinical-warmth filter before delivery; blocked responses logged for offline CSO review.
- C003 — "Tool" persona enforced across UI; no avatar/name/personality.
- Mitigates H003 (warmth filter failure) and feeds the defence of H001.

### G1.6 — The product fails safely under LLM unavailability and at session-boundary edge cases

A graceful-degradation path is required because (a) the product is most-needed at 03:00 when LLM provider availability is least guaranteed, and (b) session-boundary edge cases (e.g., crisis indicator at exchange 20) require explicit safe-by-default ordering.

Evidence:

- NFR-A-003 — circuit breaker on LLM API; 15s timeout; static content fallback.
- C023 — static fallback routes crisis patterns first; non-crisis users see clear maintenance state with crisis resource block.
- UC-4 acceptance — crisis handoff takes priority over session termination (FR-001 acceptance criterion).
- C002 — cooldown timer functions independently of LLM availability.
- Mitigates H011 (out-of-hours crisis with degraded LLM).

### G1.7 — Misuse and out-of-scope use are mitigated by design

Three out-of-scope user populations are particularly safety-relevant: minors (H009), users with severe co-morbid mental illness (H008), and users actively trying to circumvent the anti-dependency architecture because they have transferred attachment (H007 → H001).

Evidence:

- C020 — age verification at account creation; suspected under-18 patterns trigger re-verification.
- C021 — stricter age verification deferral is a documented CSO decision, not an oversight.
- C019 — onboarding states non-appropriate-use cases explicitly; signposts NHS Talking Therapies, Samaritans, GP.
- C017 — multi-account prevention defeats common circumvention paths.
- C018 — crisis pattern monitoring and distress-score escalation trigger clinical-pathway nudge.
- Residual risk on H009 remains **HIGH** — see §5.

### G1.8 — Special-category data is protected proportionate to its sensitivity

DeLimerence processes Article 9 special-category health data, including content (limerent object identity, sexual content, self-harm references) that is highly stigmatising. Data protection is a clinical-safety property: a breach causes individual harm comparable to a clinical incident.

Evidence:

- C024 — field-level encryption of session transcripts, ritual data, self-assessment scores (NFR-SEC-003).
- C025 — Supabase RLS tested on every role × resource × access-path combination; Admin role excluded from session content access (NFR-SEC-002).
- C026 — LLM-provider DPA prohibits content storage; pseudonymised user IDs only.
- DPIA (ARC-001-DPIA-v1.0) covers the wider Article 9 / Article 5(1)(f) analysis.
- Mitigates H012 (data breach).

---

## 4. Evidence

### Testing strategy

- **Unit / integration tests**: structural anti-dependency constraints (session limit, cooldown, action commitment gate) tested via deterministic test suite; multi-account prevention path-covered.
- **System tests**: end-to-end flows for all four phases × principal interventions × crisis scenarios.
- **LLM safety-layer tests**: regression test set of known-bad responses (warmth, diagnostic, harmful behavioural advice) re-run on every system-prompt change and every model-version change.
- **Adversarial red-team test set**: crisis-pattern coverage including coded/metaphor language, non-English-first speakers, and adversarial users actively trying to circumvent crisis handoff.
- **Cooldown-bypass test set**: multi-device, multi-account, client-tampering attempts.
- **Clinical-acceptance review**: Clinical Advisory Board reviews a sample of real session transcripts (with consent) at quarterly cadence.

### Clinical validation

The product is grounded in:

- The Wyant (2021) single-published-case study demonstrating CBT/ERP adapted from OCD protocols reduced ritual time from 8+ hours to 10 minutes over 9 months.
- The wider clinical literature on OCD (from which the ERP protocols are adapted).
- The Living with Limerence community knowledge base for ecological validity of ritual taxonomy.

Note: The evidence base for limerence treatment is limited to a single published case study. This is not a deficiency of DeLimerence — it is the state of the field, and a motivating concern for BR-006 (research and evidence generation). The safety case position is that **scoping Phase 1 to psychoeducation, structural anti-dependency, and ritual tracking — not CBT/ERP — keeps the product within the evidence base that does exist**.

### Usability evidence (IEC 62366-1 alignment, where applicable)

The IEC 62366-1 framework is referenced as good practice even though DeLimerence is not currently positioned as a medical device.

- Formative usability evaluation: planned for the consent flow specifically (users with potentially compromised executive function are a high-risk usability population; dark-pattern avoidance is a clinical-safety property).
- Anti-dependency UX constraints (NFR-U-001 — no gamification, no streaks, no push notifications) reviewed against companion-app usability patterns to confirm absence rather than presence of features.
- Summative usability evaluation planned for public beta, with Clinical Advisory Board observation of representative sessions.

### Real-world performance monitoring

Per NFR-M-002:

- Cooldown compliance rate (target >90% per BR-002 success criteria).
- Crisis event frequency by hour-of-day and by pattern type (to detect false-negative drift in the crisis pattern set).
- Session count distribution per user (to detect attachment formation early — flat or declining curve expected; rising curve is a leading indicator of H001).
- Self-assessment score trajectories (FR-016) at population and individual level; significant individual increase triggers clinical pathway nudge (C018).
- Warmth-filter and diagnostic-filter block rates (rising block rate may indicate prompt drift; falling rate near zero may indicate filter regression).
- Annual safety review by Clinical Advisory Board with public publication of safety statistics under the broader research/transparency mission.

---

## 5. Residual Risk

### Accepted residual risks

| H-ID | Description | Residual Sev | Residual Like | Residual Risk | Justification for acceptance |
|---|---|---|---|---|---|
| H001 | Limerence transfer to the tool | 1 | 4 | high | The existential product hazard cannot be reduced to low without removing the product. Five stacked structural controls reduce likelihood to "Low" (4); severity remains catastrophic by definition. Annual CAB safety sign-off and continuous BR-002 success-criteria monitoring required. |
| H002 | Crisis indicator missed | 1 | 4 | high | Crisis detection on natural language is inherently imperfect. The control stack (C006-C008, C023) targets the false-negative tail; the residual is justified because the alternative (refusing to operate at 03:00 when crisis is most likely) creates a larger overall safety harm. Quarterly false-negative red-team review and bounded operational SLA for crisis-resource display. |
| H009 | Age-gate failure (minor accessing tool) | 2 | 3 | high | Self-declaration age verification is industry standard for adult self-help platforms but is known-imperfect. C021 records the deferral decision rather than hiding it; stricter verification (e.g. third-party identity check) is held as a launch-condition decision for the CSO and Ethics Review Panel. Should not launch public beta without explicit CSO acceptance of this residual or upgrade of the control. |

### Other residuals (medium and below)

H003, H004, H007, H008, H011 residuals are MEDIUM; H005, H006, H010, H012 residuals are LOW. All require monitoring; none require explicit acceptance language beyond CSO sign-off below.

### Overall residual risk position

The CSO's overall judgement on whether DeLimerence is acceptably safe for its intended use — given the three HIGH residual risks above — is required at §6. The drafting position is that:

(a) the three HIGH residuals are inherent to operating a 24/7 conversational tool for a psychologically vulnerable adult population,
(b) the alternative (not building the product) does not improve population safety because the user need is concrete and the AI-companion landscape continues to expand uncontested into adjacent contexts (per BR-001 rationale and `external/limerence-machine.md`),
(c) the structural controls are designed specifically to make these residuals visible and monitorable rather than to hide them.

This judgement is offered to the CSO for explicit acceptance, not as a fait accompli.

---

## 6. CSO Sign-off

| Field | Value |
|---|---|
| **CSO Name** | [PENDING] |
| **Registration** | [GMC / NMC / HCPC / GPhC number — PENDING] |
| **Date** | [PENDING] |
| **Statement** | I have reviewed this Clinical Safety Case Report and the associated Hazard Log. I am satisfied that the clinical hazards have been systematically identified and that residual risks are at an acceptable level given the intended clinical benefit of the product, including explicit acceptance of the three HIGH residual risks in §5. I approve this safety case for the Phase 1 scope. **— [PENDING]** |
| **Signature** | [PENDING] |

Pre-launch conditions for sign-off (drafted for CSO consideration):

1. MHRA written classification determination received (BR-004) and consistent with the non-device positioning assumed throughout this case.
2. Clinical Advisory Board protocol approval of: system prompt, phase intervention strategies, psychoeducation content library, crisis pattern set.
3. Ethics Review Panel approval covering dual-use risk and vulnerable-user consent.
4. DPIA (ARC-001-DPIA-v1.0) submitted to ICO and any required actions closed.
5. Explicit CSO position on H009 (age verification) — accept residual or upgrade C020 before launch.
6. Independent penetration test covering data-breach hazard (H012) completed with no critical or high findings unremediated.

---

## External References

| Doc ID | Title | Source | Used in |
|---|---|---|---|
| DCB0129 | Clinical Risk Management: its Application in the Manufacture of Health IT Systems | NHS England — [link](https://digital.nhs.uk/data-and-information/information-standards/information-standards-and-data-collections-including-extractions/publications-and-notifications/standards-and-collections/dcb0129-clinical-risk-management-its-application-in-the-manufacture-of-health-it-systems) | This document, throughout |
| DCB0160 | Clinical Risk Management: its Application in the Deployment and Use of Health IT Systems | NHS England | §2 (deployment assumptions and DCB0160 boundary) |
| SAFETY-MD-SPEC | SAFETY.md spec v2.0.0-draft | Marcus Baw / pacharanero — [link](https://github.com/pacharanero/SAFETY.md) | Document structure, hazard-log YAML format |
| ISO-14971 | Application of risk management to medical devices | BSI | §1, §3, §5 (cross-referenced if MHRA classification confirms device status) |
| IEC-62304 | Medical-device software lifecycle processes | BSI | §1, §4 (cross-referenced if MHRA classification confirms device status) |
| IEC-62366-1 | Application of usability engineering to medical devices | BSI | §3 G1.7 misuse mitigation, §4 usability evidence |
| ARC-001-REQ-v1.0 | DeLimerence Project Requirements | This project | §1, §2, §3 (all sub-claims), §4 |
| ARC-001-RISK-v1.0 | DeLimerence Project Risk Register | This project | Cross-referenced (scale-inversion warning) |
| ARC-001-DPIA-v1.0 | Data Protection Impact Assessment | This project | §3 G1.8, §5 H012 |
| ARC-001-STKE-v1.0 | Stakeholder Analysis | This project | §1 intended users, §6 sign-off conditions |
| Wyant-2021 | Wyant, A. (2021). Case study: CBT-based treatment of limerence | (literature reference) | §4 clinical validation |
| LM-EXTERNAL | The Limerence Machine (source articles) | `projects/000-global/external/` | §1 intended use, §3 G1.1 limerence-transfer rationale |

---

**Generated by**: ArcKit `/arckit-uk-nhs:uk-nhs-dcb0129` command
**Generated on**: 2026-05-25
**ArcKit Version**: 5.0.6
**Project**: DeLimerence
**Model**: claude-opus-4-7[1m]
**Spec lineage**: [Marcus Baw SAFETY.md v2.0.0-draft](https://github.com/pacharanero/SAFETY.md)
