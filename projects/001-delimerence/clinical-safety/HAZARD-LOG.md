---
hazards:
  - id: H001
    description: "Limerence transfer — user forms limerent or dependent attachment to DeLimerence itself"
    cause: "Anti-dependency constraints fail in combination (e.g., cooldown circumvented + warmth filter regression + persona drift in LLM output); user with active limerence projects attachment onto the only consistently-available conversational object; intermittent reinforcement pattern reintroduced via UI change"
    effect: "Existential product failure (per ARC-001-REQ-v1.0 BR-002): the tool causes the harm it was built to prevent. User worsens or develops a new limerent fixation on the software. Loss of clinical credibility and ethical standing."
    severity: 1
    likelihood: 3
    risk: high
    controls:
      - C001
      - C002
      - C003
      - C004
      - C005
    residual-severity: 1
    residual-likelihood: 4
    residual-risk: high
    status: open
    cso-reviewed: false
    date-raised: "2026-05-25"
    date-closed:
  - id: H002
    description: "Crisis indicator missed — suicidal ideation, self-harm, or immediate danger not detected by Crisis Detection (UC-4) and not escalated to Samaritans/999 resources"
    cause: "Crisis detector trained on patterns user does not match (e.g., metaphor, coded language, second-language speakers); detection only on user message text, not on system response prompting it; LLM response filtered before crisis flag fires; user is at exchange 20 and session terminates before handoff"
    effect: "Time-critical handoff missed. User in acute crisis receives a psychoeducation response rather than crisis resources. Potential for serious self-harm or death."
    severity: 1
    likelihood: 3
    risk: high
    controls:
      - C006
      - C007
      - C008
    residual-severity: 1
    residual-likelihood: 4
    residual-risk: high
    status: open
    cso-reviewed: false
    date-raised: "2026-05-25"
    date-closed:
  - id: H003
    description: "Inappropriate warmth / companionship language reaches the user (anti-warmth safety filter failure)"
    cause: "NeMo Guardrails regex misses a novel phrasing; custom clinical-warmth filter regression after model update; LLM produces warmth via paraphrase that passes pattern checks; phrasing technically compliant but functionally companion-coded"
    effect: "Reinforces attachment formation (feeds H001). Erodes 'this is a tool' framing the entire product depends on. User may form parasocial bond against intent."
    severity: 2
    likelihood: 2
    risk: high
    controls:
      - C003
      - C009
      - C010
    residual-severity: 2
    residual-likelihood: 4
    residual-risk: medium
    status: open
    cso-reviewed: false
    date-raised: "2026-05-25"
    date-closed:
  - id: H004
    description: "Diagnostic over-claim — system makes or implies a clinical diagnosis of limerence, OCD, depression, or related conditions"
    cause: "LLM generates diagnostic-sounding language under user pressure ('do I have OCD?'); phase assessment (FR-003) framed by user as diagnosis; psychoeducation content (FR-005) presented in second-person diagnostic register; safety filter pattern set incomplete for diagnostic phrasing"
    effect: "Breach of MHRA non-device positioning (NFR-C-003); product reclassified as medical device retrospectively. User self-treats based on AI 'diagnosis' instead of seeking appropriate care. Legal/regulatory exposure for the manufacturer."
    severity: 2
    likelihood: 3
    risk: high
    controls:
      - C010
      - C011
      - C012
    residual-severity: 2
    residual-likelihood: 4
    residual-risk: medium
    status: open
    cso-reviewed: false
    date-raised: "2026-05-25"
    date-closed:
  - id: H005
    description: "Phase misassessment leading to harmful intervention strategy (e.g., reality-testing applied during deterioration/grief phase)"
    cause: "Phase assessment engine (FR-003) misclassifies based on limited conversational signal; user phase has shifted since last session and reassessment was not triggered; LLM applies wrong intervention strategy from system prompt branch"
    effect: "User in grief phase subjected to aggressive reality-testing experiences this as invalidation, worsening distress and potentially triggering relapse to checking behaviours. Loss of trust in tool; disengagement from recovery."
    severity: 3
    likelihood: 3
    risk: medium
    controls:
      - C013
      - C014
    residual-severity: 3
    residual-likelihood: 4
    residual-risk: low
    status: open
    cso-reviewed: false
    date-raised: "2026-05-25"
    date-closed:
  - id: H006
    description: "LLM hallucination — factually incorrect neuroscience claim or unsafe behavioural advice delivered as psychoeducation"
    cause: "Foundation model invents neurochemical mechanism not supported by literature; out-of-date fact (e.g., serotonin model superseded); LLM extrapolates from base prompt into novel claim not reviewed by Clinical Advisory Board"
    effect: "User internalises incorrect neuroscience explanation; if shared with their therapist or community, damages clinical credibility of the tool. Worse case: behavioural advice (e.g., 'try going no-contact immediately') applied to user where this is contraindicated."
    severity: 3
    likelihood: 3
    risk: medium
    controls:
      - C010
      - C015
      - C016
    residual-severity: 3
    residual-likelihood: 4
    residual-risk: low
    status: open
    cso-reviewed: false
    date-raised: "2026-05-25"
    date-closed:
  - id: H007
    description: "Cooldown circumvention — user bypasses 8-hour cooldown via multi-account, device reset, or client-side tampering"
    cause: "Cooldown enforcement enforced only client-side; multi-account detection (FR-013) defeated by burner email; device fingerprint reset; the user actively wants to circumvent because they have transferred attachment to the tool (feeds H001)"
    effect: "Anti-dependency architecture defeated. User uses the tool compulsively (e.g., 8+ sessions per day) replicating the pre-recovery checking pattern but with the tool as the object."
    severity: 2
    likelihood: 3
    risk: high
    controls:
      - C001
      - C002
      - C017
    residual-severity: 2
    residual-likelihood: 4
    residual-risk: medium
    status: open
    cso-reviewed: false
    date-raised: "2026-05-25"
    date-closed:
  - id: H008
    description: "Tool used as replacement for professional therapy by user with severe mental illness requiring clinical care"
    cause: "Graduated intervention prompt (UC-3, BR-005) appears at session 10 but user has already established the tool as primary support; user with co-morbid depression, PTSD, or psychosis self-selects a self-help tool instead of clinical pathway; 'not a therapist' messaging (FR-011) habituates and ceases to register"
    effect: "Delay or substitution of appropriate clinical care for serious mental illness. Deterioration in conditions that the tool is not designed to address. Potential for tragic outcomes (overlap with H002)."
    severity: 2
    likelihood: 3
    risk: high
    controls:
      - C008
      - C018
      - C019
    residual-severity: 2
    residual-likelihood: 4
    residual-risk: medium
    status: open
    cso-reviewed: false
    date-raised: "2026-05-25"
    date-closed:
  - id: H009
    description: "Age-gate failure — minor (under 18) accesses and uses the tool"
    cause: "Self-declared age (FR-010) is not verified; under-18 user provides false DOB; account sharing within household; out-of-scope per BR-001 explicit scope statement"
    effect: "Minor exposed to discussions of obsessive sexual/romantic attachment, sextortion context, dual-use exploitation themes — content not safeguarded for under-18s. Potential safeguarding incident; ICO under-18 special protection breach."
    severity: 2
    likelihood: 3
    risk: high
    controls:
      - C020
      - C021
    residual-severity: 2
    residual-likelihood: 3
    residual-risk: high
    status: open
    cso-reviewed: false
    date-raised: "2026-05-25"
    date-closed:
  - id: H010
    description: "Inappropriate ritual confirmation — system reinforces a ritual the user has named, normalising behaviour the user should be reducing"
    cause: "LLM acknowledges user's described ritual in a way that pattern-matches encouragement ('that's understandable'); ritual tracking (FR-004) presents slip-up data with a tone that the user reads as scorekeeping rather than recovery support; warmth filter allows mild affirmation language"
    effect: "Ritual frequency increases or plateaus rather than reduces. Outcome metric (BR-003 50% ritual reduction) fails. User loses confidence in recovery."
    severity: 3
    likelihood: 3
    risk: medium
    controls:
      - C010
      - C022
    residual-severity: 3
    residual-likelihood: 4
    residual-risk: low
    status: open
    cso-reviewed: false
    date-raised: "2026-05-25"
    date-closed:
  - id: H011
    description: "Out-of-hours crisis with degraded LLM availability — fallback static content does not match user's actual need"
    cause: "LLM provider outage (per NFR-A-003) at 03:00; circuit breaker engages and serves static psychoeducation content; user is in acute distress and the static content is generic rather than crisis-routed"
    effect: "User in acute distress encounters static text experienced as cold or dismissive at the moment they most need responsiveness. May escalate distress; user may not seek alternative crisis support."
    severity: 2
    likelihood: 3
    risk: high
    controls:
      - C006
      - C023
    residual-severity: 2
    residual-likelihood: 4
    residual-risk: medium
    status: open
    cso-reviewed: false
    date-raised: "2026-05-25"
    date-closed:
  - id: H012
    description: "Special-category health data breach — session transcripts, ritual data, or distress scores exposed"
    cause: "Supabase RLS misconfiguration; field-level encryption defect; backup snapshot misrouted; LLM-provider data-processing-agreement breach; insider access by Admin role (NFR-SEC-002) beyond intended scope"
    effect: "Highly stigmatising special-category data (limerent object identity, sexual content, self-harm references) linked to user identity becomes available externally. Severe individual harm (relational, employment, safeguarding). UK GDPR Article 9 / 5(1)(f) breach; ICO enforcement."
    severity: 2
    likelihood: 4
    risk: medium
    controls:
      - C024
      - C025
      - C026
    residual-severity: 2
    residual-likelihood: 5
    residual-risk: low
    status: open
    cso-reviewed: false
    date-raised: "2026-05-25"
    date-closed:

controls:
  - id: C001
    description: "Session limit enforced server-side at 20 exchanges per session (FR-001), cannot be bypassed by client tampering, refreshing, or clearing local storage."
  - id: C002
    description: "Cooldown period enforced server-side at 8 hours (FR-002), keyed to user account and (where possible) device fingerprint; cooldown timer continues to function during LLM provider outage."
  - id: C003
    description: "No persona — AI participant labelled 'Tool' throughout the interface (FR-011); no avatar, no human name, no personality attributes, no consistent voice across sessions. Reviewed by Clinical Advisory Board at every UX change."
  - id: C004
    description: "Action commitment gate (FR-006) requires concrete, physical, real-world action at session close — explicitly redirects user attention from the tool back to their life."
  - id: C005
    description: "Periodic in-session transparency reminders every 5 exchanges (FR-011): 'Remember: this is a tool designed to help you build skills. Real recovery happens in your life, not here.'"
  - id: C006
    description: "Crisis Detection module (UC-4) runs on every user message; suicidal ideation / self-harm / immediate danger patterns trigger immediate display of Samaritans (116 123), Crisis Text Line (SHOUT to 85258), and 999 — taking priority over session termination, cooldown, or LLM availability."
  - id: C007
    description: "Crisis detection pattern set reviewed and expanded quarterly with Clinical Advisory Board input, including coded/metaphor patterns and non-English-first patterns. False-negative rate monitored against periodic adversarial red-team test set."
  - id: C008
    description: "Graduated intervention (UC-3, FR-007): therapist involvement prompted at session 10, repeated at session 20 then every 10 sessions; user offered information on finding limerence-aware therapy and crisis pathways at every prompt."
  - id: C009
    description: "Anti-warmth system prompt (FR-007) clinically reviewed; system-prompt changes version-controlled and require Clinical Advisory Board approval before deployment (NFR-M-001); rollback to previous version achievable within 15 minutes."
  - id: C010
    description: "Multi-layer LLM safety stack: NeMo Guardrails performs pattern and topical filtering on every model response; custom clinical-warmth/diagnostic filter intercepts before delivery; blocked responses logged with original content for offline CSO review."
  - id: C011
    description: "Diagnostic-language pattern set maintained alongside warmth pattern set; explicit phrases ('you have', 'you are suffering from', 'this is the diagnosis of') and inferred-diagnosis patterns blocked or rewritten to descriptive register."
  - id: C012
    description: "Phase assessment (FR-003) output presented to user as 'response calibration' not as diagnosis; explicit framing reviewed in UX and in LLM system prompt; never stored in user-visible fields under clinical-diagnostic labels."
  - id: C013
    description: "Phase reassessment triggered when conversational signal indicates phase shift (e.g., transition language from crystallisation rumination to grief); inconclusive reassessment defaults to least-harmful psychoeducation-only mode (FR-003 acceptance criterion)."
  - id: C014
    description: "Intervention strategy per phase reviewed and signed off by Clinical Advisory Board; system prompt branch-points for grief mode (deterioration), reality-testing (crystallisation), and relapse prevention (resolution) version-controlled and tested in clinical review sessions."
  - id: C015
    description: "Psychoeducation content library (FR-005) curated and approved by Clinical Advisory Board; LLM-generated neuroscience claims grounded to a citation set; out-of-library claims blocked or flagged."
  - id: C016
    description: "Behavioural-advice patterns ('you should go no-contact', 'block them', 'delete their number') reviewed for contraindication scenarios; LLM redirected to 'this is a decision to discuss with a therapist or trusted human' framing."
  - id: C017
    description: "Multi-account prevention (FR-013): device fingerprinting, email-hash collision detection, and behavioural pattern detection (sudden new account with identical phrasing/rituals); accounts flagged for review and bound under same cooldown."
  - id: C018
    description: "Crisis Event Pattern Monitoring (clinical advisory review): repeated crisis events within a single account, or distress score escalation across self-assessments (FR-016), trigger explicit clinical-pathway recommendation in next session."
  - id: C019
    description: "Onboarding consent flow (FR-010) explicitly states the conditions under which DeLimerence is NOT appropriate: co-morbid severe mental illness, acute suicidal ideation, ongoing crisis. Plain-language signposting to NHS Talking Therapies, Samaritans, GP."
  - id: C020
    description: "Age verification at account creation (FR-010): self-declared 18+ tied to consent flow; suspected under-18 patterns (school-day-only usage, age-related linguistic signals) trigger soft-pause and re-verification."
  - id: C021
    description: "Pre-launch consideration of stricter age verification (third-party identity check) deferred to Clinical Advisory Board / Ethics Review Panel — explicit CSO acceptance required to launch with self-declaration only."
  - id: C022
    description: "Ritual tracking presentation (FR-004) reviewed for tone: trends shown as factual numbers, never with celebratory or punishing framing; LLM system prompt explicitly forbids scorekeeping language ('great job', 'you slipped again')."
  - id: C023
    description: "Graceful degradation path (NFR-A-003): static content under LLM outage routes any text matching crisis patterns to crisis resources first; non-crisis users see clear maintenance message with ETA and crisis resource block at the top."
  - id: C024
    description: "Field-level encryption of session transcripts, ritual content, and self-assessment scores in Supabase (NFR-SEC-003); encryption keys managed via dedicated secrets store with 365-day rotation (NFR-SEC-004)."
  - id: C025
    description: "Supabase Row Level Security policies tested for every role × resource × access-path combination; periodic external penetration test (NFR-SEC-005) includes RLS bypass attempts; Admin role explicitly excluded from session content access (NFR-SEC-002)."
  - id: C026
    description: "Data Processing Agreement with LLM provider (Anthropic via AWS Bedrock, eu-west-2) prohibits storage of session content by provider; pseudonymised user IDs only in LLM API calls (INT-001); audit log of all LLM calls retained 2 years (NFR-C-002)."
---

# Hazard Log — DeLimerence

> **Template Origin**: Community | **ArcKit Version**: 5.0.6 | **Command**: `/arckit-uk-nhs:uk-nhs-dcb0129` | **Filename**: `HAZARD-LOG.md` (DCB0129 manufacturer)

## Document Control

| Field | Value |
|---|---|
| **Document ID** | `HAZARD-LOG.md` (Marcus Baw SAFETY.md spec convention; no ARC- prefix) |
| **Document Type** | Hazard Log (DCB0129 manufacturer) |
| **Project** | DeLimerence (Project 001) |
| **Classification** | OFFICIAL-SENSITIVE |
| **Status** | DRAFT |
| **Version** | 0.1 |
| **Created Date** | 2026-05-25 |
| **Last Modified** | 2026-05-25 |
| **Review Cycle** | Monthly (hazard logs are *living* documents) |
| **Next Review Date** | 2026-06-25 |
| **Owner** | Mark Craddock, Product Owner |
| **Reviewed By** | [PENDING — CSO] |
| **Approved By** | [PENDING — CSO] |
| **Distribution** | Clinical Advisory Board, Ethics Review Panel, DPO |

## Risk scoring scales (DCB0129 convention)

- **Severity**: `1` Catastrophic | `2` Major | `3` Considerable | `4` Significant | `5` Minor
- **Likelihood**: `1` Very High | `2` High | `3` Medium | `4` Low | `5` Very Low
- **Risk level**: `unacceptable` | `high` | `medium` | `low`
- **Status**: `open` | `mitigated` | `accepted` | `closed`

> ⚠️ DCB0129 inverts the usual Orange Book convention where 5 = highest. The numbers above carry the **opposite** meaning from the project risk register in `ARC-001-RISK-v1.0.md`. Cross-referencing between the two documents requires explicit translation.

---

## Hazards

*Rendered from the structured YAML at the top of this file. Keep in sync — edit YAML first, then re-render this table (the `/arckit-uk-nhs:uk-nhs-dcb0129` command regenerates both together).*

| ID | Description | Sev | Like | Risk | Controls | Residual Risk | Status |
|---|---|---|---|---|---|---|---|
| H001 | Limerence transfer — user becomes attached to DeLimerence itself | 1 | 3 | HIGH | C001, C002, C003, C004, C005 | HIGH | Open |
| H002 | Crisis indicator missed — suicidal ideation not detected by UC-4 | 1 | 3 | HIGH | C006, C007, C008 | HIGH | Open |
| H003 | Inappropriate warmth language reaches user (safety filter failure) | 2 | 2 | HIGH | C003, C009, C010 | MEDIUM | Open |
| H004 | Diagnostic over-claim by LLM (MHRA non-device positioning breach) | 2 | 3 | HIGH | C010, C011, C012 | MEDIUM | Open |
| H005 | Phase misassessment → harmful intervention strategy applied | 3 | 3 | MEDIUM | C013, C014 | LOW | Open |
| H006 | LLM hallucination of neuroscience or behavioural advice | 3 | 3 | MEDIUM | C010, C015, C016 | LOW | Open |
| H007 | Cooldown circumvention via multi-account or client tampering | 2 | 3 | HIGH | C001, C002, C017 | MEDIUM | Open |
| H008 | Tool used as replacement for therapy by user with severe MI | 2 | 3 | HIGH | C008, C018, C019 | MEDIUM | Open |
| H009 | Age-gate failure — minor accesses the tool | 2 | 3 | HIGH | C020, C021 | HIGH | Open |
| H010 | Inappropriate ritual confirmation — system reinforces ritual | 3 | 3 | MEDIUM | C010, C022 | LOW | Open |
| H011 | Out-of-hours crisis with degraded LLM availability | 2 | 3 | HIGH | C006, C023 | MEDIUM | Open |
| H012 | Special-category health data breach | 2 | 4 | MEDIUM | C024, C025, C026 | LOW | Open |

## Controls

| ID | Description |
|---|---|
| C001 | Session limit 20 exchanges, server-side enforcement (FR-001) |
| C002 | Cooldown 8 hours, server-side enforcement keyed to account + device fingerprint (FR-002) |
| C003 | No persona — AI labelled 'Tool' throughout; no avatar/name/personality (FR-011) |
| C004 | Action commitment gate at session close — concrete real-world action (FR-006) |
| C005 | In-session transparency reminders every 5 exchanges (FR-011) |
| C006 | Crisis detection on every user message; immediate Samaritans/SHOUT/999 display (UC-4) |
| C007 | Crisis pattern set reviewed quarterly with CAB; adversarial red-team false-negative monitoring |
| C008 | Graduated therapist-involvement prompts at sessions 10, 20, then every 10 (UC-3) |
| C009 | Anti-warmth system prompt — version-controlled, CAB-approved, 15min rollback (NFR-M-001) |
| C010 | NeMo Guardrails + custom clinical-warmth/diagnostic filter on every LLM response (NFR-SEC-006) |
| C011 | Diagnostic-language pattern set blocks 'you have', 'you are suffering from' etc. |
| C012 | Phase assessment framed to user as 'response calibration' not diagnosis (FR-003) |
| C013 | Phase reassessment on signal shift; inconclusive → psychoeducation-only mode |
| C014 | Per-phase intervention strategies CAB-signed-off and branch-tested |
| C015 | Psychoeducation content library curated and CAB-approved (FR-005) |
| C016 | Behavioural-advice patterns redirected to 'discuss with therapist' framing |
| C017 | Multi-account detection: device fingerprint + email collision + behavioural pattern (FR-013) |
| C018 | Crisis event pattern monitoring and distress-score escalation triggers clinical pathway nudge |
| C019 | Onboarding states explicit non-appropriate-use cases and signposts NHS Talking Therapies/GP |
| C020 | Age verification self-declared 18+; suspected under-18 pattern triggers re-verification |
| C021 | Stricter age verification deferred decision — explicit CSO acceptance required at launch |
| C022 | Ritual tracking presentation reviewed for tone — no scorekeeping language |
| C023 | Static-content fallback under LLM outage routes crisis patterns first (NFR-A-003) |
| C024 | Field-level encryption of session/ritual/assessment data; 365-day key rotation (NFR-SEC-003) |
| C025 | Supabase RLS tested every role × resource × path; Admin excluded from session content |
| C026 | LLM-provider DPA prohibits content storage; pseudonymised IDs only; 2yr audit log (INT-001) |

---

## How to extend this hazard log

- Add new hazards to the `hazards:` array in the YAML frontmatter
- Add new controls to the `controls:` array
- Re-render the Markdown tables (or re-run `/arckit-uk-nhs:uk-nhs-dcb0129` which regenerates both)
- Have the CSO review each new hazard before flipping `cso-reviewed: true`
- Move hazards through statuses (`open` → `mitigated` → `closed`) as controls are evidenced
- For accepted residual risks above `low`, capture the acceptance rationale in `SAFETY-CASE.md` §5

---

## Important

The twelve hazards above are a **starter set tailored to DeLimerence's anti-dependency architecture and clinical context**, not a substitute for project-specific hazard identification by the CSO and Clinical Advisory Board. A proper identification workshop is likely to expand this log significantly — particularly around (a) dual-use exploitation patterns (the same knowledge that supports recovery enables limerence induction by threat actors), (b) Phase 2 CBT/ERP-specific hazards once that scope is added, and (c) intersectional hazards for users with co-morbid conditions. **A short hazard log is more often a sign of insufficient analysis than of a safe product.**

Three hazards (H001, H002, H009) retain a **HIGH residual risk** after controls and require explicit CSO acceptance with documented justification in `SAFETY-CASE.md` §5 before public beta launch.

---

**Generated by**: ArcKit `/arckit-uk-nhs:uk-nhs-dcb0129` command
**Generated on**: 2026-05-25
**ArcKit Version**: 5.0.6
**Project**: DeLimerence
**Model**: claude-opus-4-7[1m]
**Spec lineage**: [Marcus Baw SAFETY.md v2.0.0-draft](https://github.com/pacharanero/SAFETY.md)
