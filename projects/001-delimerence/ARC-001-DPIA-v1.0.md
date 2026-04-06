# Data Protection Impact Assessment: DeLimerence

> **Template Origin**: Official | **ArcKit Version**: 4.6.4-rc.1 | **Command**: `/arckit:dpia`

## Document Control

| Field | Value |
|-------|-------|
| **Document ID** | ARC-001-DPIA-v1.0 |
| **Document Type** | Data Protection Impact Assessment |
| **Project** | DeLimerence (Project 001) |
| **Classification** | OFFICIAL-SENSITIVE |
| **Status** | DRAFT |
| **Version** | 1.0 |
| **Created Date** | 2026-04-06 |
| **Last Modified** | 2026-04-06 |
| **Review Cycle** | Annual (12 months) |
| **Next Review Date** | 2027-04-06 |
| **Owner** | Mark Craddock, Product Owner |
| **Data Protection Officer** | To be appointed |
| **Reviewed By** | PENDING |
| **Approved By** | PENDING |
| **Distribution** | Product Owner, DPO, Clinical Advisory Board, Ethics Review Panel |
| **ArcKit Version** | 4.6.4-rc.1 |

## Revision History

| Version | Date | Author | Changes | Approved By | Approval Date |
|---------|------|--------|---------|-------------|---------------|
| 1.0 | 2026-04-06 | ArcKit AI | Initial creation from `/arckit:dpia` command | PENDING | PENDING |

## Regulatory Basis

This DPIA is prepared in accordance with:

- **UK GDPR Article 35** -- Data protection impact assessment
- **UK GDPR Article 36** -- Prior consultation with the ICO
- **Data Protection Act 2018**, Part 2, Chapter 2
- **ICO DPIA Guidance** (2024) -- including the 9-criteria screening checklist
- **ICO AI and Data Protection Guidance** (2023)

---

## 1. Need for a DPIA

### 1.1 Screening Decision

A DPIA is **REQUIRED** under UK GDPR Article 35(1). Processing is likely to result in a high risk to the rights and freedoms of natural persons.

### 1.2 ICO 9-Criteria Screening

The ICO screening checklist identifies processing that is likely to require a DPIA. Two or more criteria met triggers a mandatory DPIA. DeLimerence meets **6 of 9 criteria**.

| # | ICO Criterion | Result | Justification |
|---|---------------|--------|---------------|
| 1 | **Evaluation or scoring** | **YES** | Phase assessment evaluates user's limerence stage (initiation, crystallisation, deterioration, resolution). Ritual tracking scores progress over time. Self-assessment instruments (DLIM-5) produce numerical scores tracking distress intensity. |
| 2 | **Automated decision-making with legal or significant effect** | **YES** | AI adapts response strategy based on assessed phase. Phase determines intervention intensity -- reality-testing for crystallisation, grief support for deterioration. While no decisions produce legal effects, they produce similarly significant effects on psychological wellbeing. |
| 3 | **Systematic monitoring** | **YES** | Ritual tracking monitors user behaviour patterns across sessions: slip counts, resistance counts, session frequency, phase progression. This constitutes systematic observation of data subjects over time. |
| 4 | **Sensitive data or data of a highly personal nature** | **YES** | Special category health data under UK GDPR Article 9. Mental health-adjacent data processed includes: limerent rituals (compulsive behaviours), phase assessments (psychological state), self-assessment scores (distress intensity), and emotional state disclosures in conversational sessions. |
| 5 | **Data processed on a large scale** | **NO** | Year 1 target: 5,000 users. Year 3 target: 100,000 registered users. Not national-scale processing. Volume is moderate, not large-scale per ICO guidance. |
| 6 | **Matching or combining datasets** | **NO** | No combining of datasets from multiple sources. All data originates from direct user interaction with the tool. No third-party data enrichment or dataset matching. |
| 7 | **Data concerning vulnerable data subjects** | **YES** | Users experiencing involuntary neurochemical states with compromised executive function. Limerence produces serotonin depletion that generates OCD-like symptoms [LM12-C3]. Users may be in acute psychological distress at 3am with impaired decision-making capacity. The ICO explicitly identifies people with mental health conditions as vulnerable data subjects. |
| 8 | **Innovative use of technology or applying existing technology to a new domain** | **YES** | Novel anti-dependency AI architecture with no precedent. LLM-based conversational tool for a condition with only one published clinical case study (Wyant, 2021). The deliberate inversion of AI companion app architecture is an unprecedented application of generative AI. |
| 9 | **Processing that prevents data subjects from exercising a right or using a service or contract** | **NO** | Data subject rights (access, deletion, portability) are implemented in requirements (FR-010, NFR-C-001). Users can withdraw consent and delete their account at any time. No processing restricts rights exercise. |

### 1.3 Screening Summary

**Criteria met: 6 of 9** (criteria 1, 2, 3, 4, 7, 8)

The threshold for a mandatory DPIA is 2 criteria. DeLimerence exceeds this significantly. The combination of special category health data (criterion 4) from vulnerable data subjects (criterion 7) using innovative technology (criterion 8) with systematic monitoring (criterion 3) and automated evaluation (criteria 1, 2) represents a high-risk processing scenario that demands thorough impact assessment.

---

## 2. Description of Processing

### 2.1 Purpose of Processing

DeLimerence is a conversational AI tool designed to help people recognise and recover from limerence -- involuntary obsessive romantic attachment characterised by intrusive thoughts, compulsive rituals, and disrupted executive function. It uses CBT (Cognitive Behavioural Therapy), ERP (Exposure and Response Prevention), and psychoeducation to systematically loosen attachment, adapted from the clinical protocol described in the only published case study on limerence treatment (Wyant, 2021).

The tool is the deliberate inversion of AI companion apps (Replika, Character.ai). Where companion apps deepen emotional attachment through intermittent reinforcement and simulated emotional presence, DeLimerence employs an anti-dependency architecture with 9 structural constraints designed to prevent users from forming attachment to the tool itself [ADR-002].

**Processing purposes:**

1. **Conversational intervention** -- Conduct phase-aware conversations using CBT/ERP techniques to help users interrupt limerent rumination and reduce ritual behaviour
2. **Phase assessment** -- Evaluate user's current limerence phase to calibrate intervention strategy (initiation, crystallisation, deterioration, resolution)
3. **Ritual tracking** -- Monitor user-reported compulsive behaviours (slips and resistances) across sessions to measure progress
4. **Self-assessment** -- Administer and score periodic instruments (DLIM-5) to track distress intensity over time
5. **Crisis detection** -- Identify indicators of suicidal ideation or self-harm to provide appropriate crisis resources
6. **Research** -- Generate anonymised, aggregated outcome data for academic research into limerence treatment (opt-in only, separate consent)

### 2.2 Nature of Processing

| Processing Activity | Data Categories | Legal Basis | Recipients |
|---------------------|----------------|-------------|------------|
| Account creation and authentication | User profile (DR-001) | Art. 6(1)(a) Consent | Supabase Auth (ADR-005) |
| Conversational sessions via LLM | Session data (DR-002), user disclosures | Art. 6(1)(a) + Art. 9(2)(a) Explicit consent | AWS Bedrock/Claude (ADR-001) -- zero-retention DPA |
| Phase assessment | Phase classification (DR-002) | Art. 6(1)(a) + Art. 9(2)(a) Explicit consent | Application layer only |
| Ritual tracking | Ritual records (DR-003) | Art. 6(1)(a) + Art. 9(2)(a) Explicit consent | Supabase PostgreSQL (ADR-006) |
| Self-assessment scoring | Assessment scores (DR-004) | Art. 6(1)(a) + Art. 9(2)(a) Explicit consent | Supabase PostgreSQL (ADR-006) |
| Crisis detection | Session content (DR-002) | Art. 6(1)(d) Vital interests | Safety layer (ADR-003) -- no data retained |
| Anonymised research export | Anonymised aggregates | Art. 6(1)(a) + Art. 9(2)(j) Research | Academic partners (with data sharing agreement) |

### 2.3 Scope of Processing

- **Data subjects**: Adults (18+) experiencing limerence who voluntarily seek recovery support
- **Volume**: Year 1: ~5,000 registered users, ~50,000 sessions. Year 2: ~25,000 registered users, ~500,000 sessions. Year 3: ~100,000 registered users
- **Geographic scope**: UK-based service with UK data residency (TC-1, ADR-008). All processing occurs within AWS eu-west-2 (London) and Supabase UK region
- **Duration**: Processing continues while account is active. Session data retained for 12 months. Account data deleted within 30 days of deletion request
- **Frequency**: Users may access the tool at any time, subject to 8-hour cooldown between sessions (maximum ~3 sessions per day)

### 2.4 Data Entities

#### DR-001: User Profile

| Attribute | Type | Sensitivity | Purpose |
|-----------|------|-------------|---------|
| user_id | UUID | LOW | System identifier -- no inherent meaning |
| email_hash | SHA-256 | MEDIUM | Authentication -- not reversible to email |
| age_confirmed | Boolean | LOW | Age gating compliance (18+) |
| consent_general | Timestamp | LOW | Consent audit trail |
| consent_research | Timestamp (nullable) | LOW | Research consent audit trail (48hr delay) |
| therapist_involved | Boolean | MEDIUM | Clinical pathway flag (set at session 10+) |
| created_at | Timestamp | LOW | Account lifecycle |
| deleted_at | Timestamp (nullable) | LOW | Soft deletion audit |

**Classification**: CONFIDENTIAL | **Retention**: Active while account exists; deleted within 30 days of deletion request

#### DR-002: Session Data

| Attribute | Type | Sensitivity | Purpose |
|-----------|------|-------------|---------|
| session_id | UUID | LOW | Session identifier |
| user_id | UUID | LOW | Links to user profile |
| started_at / ended_at | Timestamp | LOW | Session duration tracking |
| exchange_count | Integer (max 20) | LOW | Anti-dependency constraint compliance |
| phase_assessed | Enum | HIGH | Psychological state assessment |
| interventions_used | Array | MEDIUM | Clinical intervention audit |
| action_commitment | Text (max 500) | HIGH | User's stated real-world action |
| crisis_event | Boolean | HIGH | Crisis detection audit |

**Classification**: CONFIDENTIAL (special category -- health data) | **Retention**: 12 months full records; summary retained while account active

#### DR-003: Ritual Tracking Data

| Attribute | Type | Sensitivity | Purpose |
|-----------|------|-------------|---------|
| tracking_id | UUID | LOW | Record identifier |
| user_id | UUID | LOW | Links to user profile |
| ritual_name | String (user-defined) | HIGH | User-defined label for compulsive behaviour |
| date | Date | LOW | Report date |
| slip_count | Integer | HIGH | Times ritual was performed |
| resist_count | Integer | MEDIUM | Times urge was resisted |
| session_id | UUID | LOW | Links to session |

**Classification**: CONFIDENTIAL (special category -- health data) | **Retention**: Summary retained while account active; raw per-session data follows session retention (12 months)

#### DR-004: Self-Assessment Scores

| Attribute | Type | Sensitivity | Purpose |
|-----------|------|-------------|---------|
| assessment_id | UUID | LOW | Record identifier |
| user_id | UUID | LOW | Links to user profile |
| session_id | UUID | LOW | Links to session |
| instrument | String | LOW | Assessment instrument (e.g., "DLIM-5") |
| total_score | Integer | HIGH | Aggregate distress/limerence score |
| item_scores | JSON | HIGH | Individual item responses |
| assessed_at | Timestamp | LOW | Assessment timestamp |

**Classification**: CONFIDENTIAL (special category -- health data) | **Retention**: Retained while account active (longitudinal trend data is clinically valuable)

### 2.5 Data Flow

```
User Device (browser/PWA)
    │
    │ TLS 1.3+ encrypted
    │
    ▼
AWS Fargate (eu-west-2, London) ──── ADR-008
    │
    ├──► Next.js Application Layer
    │       │
    │       ├──► NeMo Guardrails Safety Layer ──── ADR-003
    │       │       │
    │       │       ▼
    │       │   AWS Bedrock (eu-west-2) ──── ADR-001
    │       │       Claude LLM (zero-retention DPA)
    │       │       Pseudonymised user_id only (INT-001)
    │       │       No PII in prompts
    │       │
    │       └──► Supabase PostgreSQL (UK) ──── ADR-006
    │               Row Level Security (per-user isolation)
    │               Field-level encryption (pgcrypto)
    │               DR-001, DR-002, DR-003, DR-004
    │
    └──► Supabase Auth (UK) ──── ADR-005
            Email hash authentication
            JWT token management
```

**Key data flow controls:**

- All data in transit protected by TLS 1.3+
- LLM receives pseudonymised user_id only -- no PII transmitted to LLM provider
- LLM provider (AWS Bedrock) operates under zero-retention DPA -- no conversation data stored at rest
- All persistent data stored in Supabase PostgreSQL with Row Level Security enforcing per-user isolation
- Sensitive fields (session transcripts, ritual names) encrypted at field level using pgcrypto (ADR-006)
- All infrastructure deployed in UK (eu-west-2 London) -- no international data transfers

---

## 3. Consultation

### 3.1 Data Subject Consultation

| Consultation Method | Target Group | Status | Findings |
|---------------------|-------------|--------|----------|
| Online survey | Living with Limerence community | PLANNED | To gather views on data processing purposes, consent flow design, and acceptable data retention periods |
| Beta user feedback | Early access users | PLANNED | To validate consent comprehension, assess whether consent flow is accessible during distress, and identify unforeseen privacy concerns |
| Accessibility review | Users with compromised executive function | PLANNED | To validate that consent materials are comprehensible when cognitive capacity is impaired (Flesch-Kincaid < grade 10) |

### 3.2 Internal Consultation

| Consultee | Role | Status | Input Required |
|-----------|------|--------|----------------|
| Data Protection Officer | DPO | TO BE APPOINTED | Review and sign-off of this DPIA |
| Clinical Advisory Board | Clinical governance | TO BE CONSTITUTED | Validate clinical appropriateness of data processing purposes; review phase assessment protocol |
| Ethics Review Panel | Ethics oversight | TO BE CONSTITUTED | Review dual-use implications; assess proportionality of data collection from vulnerable users |
| Mark Craddock | Product Owner | ACTIVE | Processing purposes, architecture decisions, risk acceptance |

### 3.3 External Consultation

| Consultee | Purpose | Status |
|-----------|---------|--------|
| ICO (voluntary engagement) | Novel processing -- anti-dependency AI for vulnerable users; seek informal guidance on consent architecture for users with compromised executive function | RECOMMENDED |
| MHRA | Medical device classification determination -- impacts scope of data processing obligations | IN PROGRESS (ADR-004) |
| Academic ethics committee | Approval for research data collection and anonymised data sharing | PLANNED |

---

## 4. Necessity and Proportionality

### 4.1 Lawful Basis

| Processing Purpose | Article 6 Basis | Article 9 Basis | Justification |
|--------------------|-----------------|-----------------|---------------|
| General data processing (account, sessions) | Art. 6(1)(a) Consent | -- | Users voluntarily seek the tool and consent to data processing during onboarding |
| Special category health data (phase, rituals, scores) | Art. 6(1)(a) Consent | Art. 9(2)(a) Explicit consent | Separate, explicit consent for health data with clear explanation of what constitutes health data in this context |
| Crisis detection | Art. 6(1)(d) Vital interests | Art. 9(2)(c) Vital interests | When user expresses suicidal ideation, vital interests override consent for the purpose of displaying crisis resources |
| Anonymised research data | Art. 6(1)(a) Consent | Art. 9(2)(j) Research (with appropriate safeguards) | Opt-in, separate consent with 48-hour reflection period; ethics committee approval required; k-anonymity (minimum group size 10) |

### 4.2 Consent Architecture for Vulnerable Users

Standard consent flows may be insufficient for users with compromised executive function. The following safeguards address this:

| Safeguard | Implementation | Requirement Ref |
|-----------|---------------|-----------------|
| Plain language | All consent text at Flesch-Kincaid reading level < grade 10 | NFR-C-001 |
| No dark patterns | No pre-ticked boxes, no consent bundling, no colour-weighted buttons | NFR-U-001 |
| Layered consent | General consent separate from health data consent separate from research consent | DR-001 |
| Withdrawal at any time | Users can withdraw consent and delete account from any session | FR-010 |
| 48-hour reflection period | Research consent cannot take effect for 48 hours after opt-in, allowing users to reconsider once acute distress may have passed | DR-001 (consent_research) |
| Periodic consent reminders | System periodically reminds users what data is being processed and that they can withdraw | NFR-C-001 |
| No consent-gating | Users can access crisis resources without consenting to data processing | UC-4 |

### 4.3 Data Minimisation

| Principle | Implementation |
|-----------|---------------|
| **Collection minimisation** | Only data necessary for the stated purposes is collected. No browsing data, device telemetry, location data, or social media data. Email is hashed at point of collection -- raw email is never stored (DR-001). |
| **Processing minimisation** | LLM receives pseudonymised user_id only (INT-001). No PII is included in LLM prompts. Ritual names are stored but not analysed by AI -- they serve as user-facing labels only. |
| **Retention minimisation** | Session data auto-deleted after 12 months. Account data deleted within 30 days of deletion request. Raw ritual data follows session retention. Only summary/trend data retained long-term. |
| **Access minimisation** | Row Level Security enforces per-user data isolation at database level (ADR-006). No admin access to decrypted session content without explicit justification. |

### 4.4 Purpose Limitation

All data is processed solely for the purposes stated in Section 2.1. No secondary purposes are pursued without additional consent. Specifically:

- No advertising or marketing use of data
- No selling or sharing of data with third parties (except anonymised research data with explicit consent)
- No user profiling for commercial purposes
- No re-engagement campaigns or push notifications (BC-2, ADR-008)
- No behavioural targeting or recommendation algorithms

### 4.5 Storage Limitation

| Data Entity | Active Retention | Post-Deletion | Justification |
|-------------|-----------------|---------------|---------------|
| DR-001: User Profile | While account active | Deleted within 30 days | Only needed for active account management |
| DR-002: Session Data (full) | 12 months | Deleted with account | Full records needed for cross-session continuity; 12-month limit prevents indefinite accumulation |
| DR-002: Session Data (summary) | While account active | Deleted with account | Summary (phase, counts) needed for longitudinal tracking |
| DR-003: Ritual Tracking (raw) | 12 months | Deleted with account | Raw per-session data follows session retention |
| DR-003: Ritual Tracking (summary) | While account active | Deleted with account | Trends needed for progress visualisation |
| DR-004: Self-Assessment | While account active | Deleted with account | Longitudinal trend data is clinically valuable for tracking recovery |

---

## 5. Risk Assessment

### 5.1 Risk Methodology

Risks are assessed for their impact on **individuals** (data subjects), not on the organisation. This follows ICO DPIA guidance, which requires the assessment to focus on risks to the rights and freedoms of natural persons.

**Likelihood scale:**

| Rating | Definition |
|--------|------------|
| Remote | Unlikely to occur; no known precedent |
| Possible | Could occur; precedent exists in similar contexts |
| Probable | Likely to occur; strong precedent or structural factors make occurrence expected |

**Impact scale:**

| Rating | Definition |
|--------|------------|
| Minimal | Negligible impact on individual; easily remedied |
| Minor | Some inconvenience or distress; short-term impact |
| Significant | Material impact on wellbeing, relationships, or employment; requires effort to remedy |
| Severe | Serious harm to psychological health, safety, or fundamental rights; may be irreversible |

**Overall risk rating:**

| | Minimal | Minor | Significant | Severe |
|---|---------|-------|-------------|--------|
| **Probable** | LOW | MEDIUM | HIGH | HIGH |
| **Possible** | LOW | LOW | MEDIUM | HIGH |
| **Remote** | LOW | LOW | LOW | MEDIUM |

### 5.2 Risk Register

#### DPIA-001: Breach of Special Category Health Data

| Field | Assessment |
|-------|------------|
| **Risk ID** | DPIA-001 |
| **Risk Description** | Unauthorised access to or disclosure of special category health data (session transcripts, ritual tracking records, phase assessments, self-assessment scores) |
| **Data Categories Affected** | DR-002, DR-003, DR-004 |
| **Harm to Individuals** | Ritual tracking data reveals intimate details of obsessive behaviours (e.g., "checking [person's name]'s Instagram 47 times today"). Session transcripts contain emotional disclosures about romantic attachment. Breach could cause: psychological harm (shame, stigma associated with obsessive attachment), relationship damage (if limerent object or partner discovers content), professional harm (disclosure of compromised executive function), exploitation (blackmail or coercion using intimate behavioural data). |
| **Likelihood (Inherent)** | Possible |
| **Impact (Inherent)** | Severe |
| **Overall (Inherent)** | **HIGH** |
| **Mitigations** | Field-level encryption using pgcrypto for sensitive attributes (ADR-006); Row Level Security enforcing per-user data isolation at database level (ADR-006); UK data residency -- all data in eu-west-2 London (ADR-008); TLS 1.3+ for all data in transit; zero-retention DPA with LLM provider (ADR-001); pseudonymised user_id in LLM calls -- no PII transmitted (INT-001); email hashed at collection -- raw email never stored (DR-001); automated data retention enforcement -- session data auto-deleted at 12 months |
| **Likelihood (Residual)** | Remote |
| **Impact (Residual)** | Severe |
| **Overall (Residual)** | **MEDIUM** |
| **Risk Owner** | Data Protection Officer (to be appointed) |
| **Traceability** | R-003 (RISK), NFR-SEC-003 (REQ), ADR-006, ADR-001 |

---

#### DPIA-002: Invalid Consent from Users with Compromised Executive Function

| Field | Assessment |
|-------|------------|
| **Risk ID** | DPIA-002 |
| **Risk Description** | Consent obtained from users may not meet the UK GDPR standard of "freely given, specific, informed and unambiguous" because the user's executive function is compromised by the neurochemical effects of limerence (serotonin depletion, OCD-like symptoms) |
| **Data Categories Affected** | All (DR-001 through DR-004) |
| **Harm to Individuals** | Processing personal data -- including special category health data -- without valid legal basis. Users may later regret disclosures made during acute distress. Inability to make informed decisions about data processing at the point of most need creates a structural consent paradox: the condition that makes the tool necessary also impairs the capacity to consent to its use. |
| **Likelihood (Inherent)** | Probable |
| **Impact (Inherent)** | Significant |
| **Overall (Inherent)** | **HIGH** |
| **Mitigations** | Plain language consent at Flesch-Kincaid reading level < grade 10; no dark patterns (no pre-ticked boxes, no consent bundling, no colour-weighted buttons); layered consent (general, health data, and research consent are separate); 48-hour reflection period for research consent; periodic consent reminders during ongoing use; withdrawal available at any time from any session; consent architecture reviewed by Clinical Advisory Board for appropriateness to vulnerable users; no consent-gating of crisis resources |
| **Likelihood (Residual)** | Possible |
| **Impact (Residual)** | Significant |
| **Overall (Residual)** | **MEDIUM** |
| **Risk Owner** | Data Protection Officer (to be appointed) |
| **Traceability** | R-011 (RISK), NFR-C-001 (REQ), DR-001 |

---

#### DPIA-003: AI Profiling Creates Psychological Dependency

| Field | Assessment |
|-------|------------|
| **Risk ID** | DPIA-003 |
| **Risk Description** | Phase assessment and adaptive response strategy constitute profiling under UK GDPR. If the AI's personalised, phase-aware responses create emotional attachment to the tool, the data processing itself causes the harm it is meant to prevent -- limerence transfer from the original object to the AI tool. |
| **Data Categories Affected** | DR-002 (phase_assessed, interventions_used), DR-003 (ritual tracking patterns) |
| **Harm to Individuals** | Formation of new compulsive attachment to the tool, replacing the original limerent attachment. User becomes dependent on the tool for emotional regulation, undermining recovery. The profiling that enables personalised intervention also creates the conditions for attachment. This is the existential product risk (R-001). |
| **Likelihood (Inherent)** | Possible |
| **Impact (Inherent)** | Severe |
| **Overall (Inherent)** | **HIGH** |
| **Mitigations** | Anti-dependency architecture with 9 structural constraints enforced server-side (ADR-002): session limits (20 exchanges max), cooldown periods (8 hours minimum), no persona (AI labelled "Tool"), anti-warmth system prompt (no simulated emotional presence), action commitment gate (concrete real-world action required), graduated therapist referral (after 10+ sessions); no push notifications or re-engagement campaigns (BC-2, ADR-008 -- structurally impossible on iOS PWA); transparent AI identification -- tool explicitly states it is software, not a companion (FR-011, PRIN-012); declining session frequency monitored as safety metric; Clinical Advisory Board annual safety sign-off |
| **Likelihood (Residual)** | Remote |
| **Impact (Residual)** | Severe |
| **Overall (Residual)** | **MEDIUM** |
| **Risk Owner** | Clinical Advisory Board |
| **Traceability** | R-001 (RISK), BR-002 (REQ), ADR-002, FR-007, FR-011 |

---

#### DPIA-004: LLM Processes Sensitive Health Disclosures via Third-Party API

| Field | Assessment |
|-------|------------|
| **Risk ID** | DPIA-004 |
| **Risk Description** | User conversations sent to the LLM API (AWS Bedrock/Claude) contain health disclosures -- descriptions of obsessive thoughts, compulsive behaviours, emotional distress, and intimate relationship details. Even with a zero-retention DPA, data is processed in transit by a third-party provider. |
| **Data Categories Affected** | DR-002 (session content transmitted to LLM) |
| **Harm to Individuals** | Potential exposure of intimate health disclosures if LLM provider's zero-retention commitment fails. Loss of control over sensitive data once transmitted to third-party infrastructure. Risk amplified by the highly personal nature of limerence disclosures. |
| **Likelihood (Inherent)** | Probable |
| **Impact (Inherent)** | Significant |
| **Overall (Inherent)** | **MEDIUM** |
| **Mitigations** | Zero-retention DPA with AWS Bedrock -- no conversation data stored at rest by provider (ADR-001); pseudonymised user_id only -- no PII in LLM prompts (INT-001); UK data residency -- Bedrock processing in eu-west-2 London (ADR-001); session context is session-scoped -- LLM has no persistent memory across sessions; NeMo Guardrails safety layer filters output before delivery to user (ADR-003); regular DPA compliance audits planned |
| **Likelihood (Residual)** | Remote |
| **Impact (Residual)** | Significant |
| **Overall (Residual)** | **LOW** |
| **Risk Owner** | Product Owner |
| **Traceability** | R-010 (RISK), INT-001 (REQ), ADR-001 |

---

#### DPIA-005: Inadequate Crisis Detection Leads to User Harm

| Field | Assessment |
|-------|------------|
| **Risk ID** | DPIA-005 |
| **Risk Description** | If crisis indicators (suicidal ideation, self-harm expressions, immediate danger) are missed by the safety layer, users in acute distress may not receive appropriate crisis resources. The data processing (conversational session) continues without triggering the safety response. |
| **Data Categories Affected** | DR-002 (session content, crisis_event flag) |
| **Harm to Individuals** | User in immediate danger does not receive crisis resources (Samaritans 116 123, Crisis Text Line, 999). Failure to detect crisis could contribute to serious harm or loss of life. Users accessing the tool at 3am during acute distress are at heightened risk. |
| **Likelihood (Inherent)** | Possible |
| **Impact (Inherent)** | Severe |
| **Overall (Inherent)** | **HIGH** |
| **Mitigations** | Defence-in-depth safety layer using NeMo Guardrails with custom clinical filters (ADR-003); crisis resources (Samaritans, Crisis Text Line, 999) displayed on every screen regardless of detection (UC-4); multi-layer detection: keyword matching + semantic analysis + LLM-based assessment; crisis detection operates independently of phase assessment -- triggers at any phase; false positives preferred over false negatives (safety-first calibration); static crisis resource page accessible without login |
| **Likelihood (Residual)** | Remote |
| **Impact (Residual)** | Severe |
| **Overall (Residual)** | **MEDIUM** |
| **Risk Owner** | Clinical Advisory Board |
| **Traceability** | R-007 (RISK), UC-4 (REQ), ADR-003, FR-008 |

---

#### DPIA-006: Phase Misassessment Causes Inappropriate Intervention

| Field | Assessment |
|-------|------------|
| **Risk ID** | DPIA-006 |
| **Risk Description** | Incorrect assessment of user's limerence phase leads to phase-inappropriate intervention. Aggressive reality-testing for a user in deterioration phase could worsen grief and distress. Grief support for a user in crystallisation phase could reinforce the limerent attachment. |
| **Data Categories Affected** | DR-002 (phase_assessed, interventions_used) |
| **Harm to Individuals** | Psychological harm from receiving the wrong type of intervention at a vulnerable moment. User's distress could be exacerbated rather than reduced. Trust in the tool could be damaged, potentially preventing future help-seeking. |
| **Likelihood (Inherent)** | Possible |
| **Impact (Inherent)** | Significant |
| **Overall (Inherent)** | **MEDIUM** |
| **Mitigations** | LLM-driven phase assessment with structured output validation (ADR-007); clinical advisory board protocol review for assessment criteria; inconclusive assessment defaults to least-harmful mode (psychoeducation only -- no aggressive reality-testing) per UC-1 Alt 6a; phase reassessment available at any session; multi-factor assessment using duration, symptom presentation, and self-report; explicit disclaimer that phase assessment is response calibration, not clinical diagnosis (ADR-004) |
| **Likelihood (Residual)** | Remote |
| **Impact (Residual)** | Significant |
| **Overall (Residual)** | **LOW** |
| **Risk Owner** | Clinical Advisory Board |
| **Traceability** | R-008 (RISK), ADR-007, FR-003, UC-1 |

---

#### DPIA-007: Ritual Tracking Data Reveals Intimate Behavioural Patterns

| Field | Assessment |
|-------|------------|
| **Risk ID** | DPIA-007 |
| **Risk Description** | Ritual names are user-defined free text and may reveal highly personal information about obsessive behaviours. Examples: "checking [person's name]'s Instagram", "driving past [person's] house", "rereading [person's] messages". Longitudinal tracking (slip counts, resistance counts over weeks/months) creates a detailed temporal picture of compulsive behaviour patterns. |
| **Data Categories Affected** | DR-003 (ritual_name, slip_count, resist_count across time) |
| **Harm to Individuals** | Exposure of ritual data could reveal: the identity of the limerent object (through ritual names), the intensity and nature of obsessive behaviours (through slip/resist counts), patterns of stalking-adjacent behaviour (checking social media, engineering encounters), and the trajectory of the user's psychological state. This data is acutely stigmatising. |
| **Likelihood (Inherent)** | Possible |
| **Impact (Inherent)** | Significant |
| **Overall (Inherent)** | **MEDIUM** |
| **Mitigations** | Field-level encryption for ritual_name using pgcrypto (ADR-006); ritual names stored for user-facing display only -- not analysed by AI or included in LLM prompts; Row Level Security prevents cross-user access (ADR-006); user controls deletion of individual rituals and full account; data minimisation -- only slip_count and resist_count stored, not detailed descriptions of each incident; 12-month retention for raw data, summary only thereafter |
| **Likelihood (Residual)** | Remote |
| **Impact (Residual)** | Significant |
| **Overall (Residual)** | **LOW** |
| **Risk Owner** | Data Protection Officer (to be appointed) |
| **Traceability** | DR-003 (REQ), ADR-006, NFR-SEC-003 |

---

#### DPIA-008: Research Data Re-identification

| Field | Assessment |
|-------|------------|
| **Risk ID** | DPIA-008 |
| **Risk Description** | Anonymised research datasets shared with academic partners could potentially be re-identified, particularly given the small user population (5,000 Year 1), the rarity of limerence as a recognised condition, and the potential for unique combinations of attributes (phase, ritual types, session patterns) to identify individuals. |
| **Data Categories Affected** | Anonymised aggregates derived from DR-002, DR-003, DR-004 |
| **Harm to Individuals** | Re-identification would expose the individual's limerence status and behavioural data to researchers and potentially to the public through published research. Given the stigma associated with limerence-related behaviours, this could cause significant personal and professional harm. |
| **Likelihood (Inherent)** | Remote |
| **Impact (Inherent)** | Significant |
| **Overall (Inherent)** | **LOW** |
| **Mitigations** | k-anonymity with minimum group size of 10 -- no aggregate published if fewer than 10 individuals share the combination of attributes; separate research consent with 48-hour reflection period (DR-001, consent_research); ethics committee approval required before any data sharing; formal data sharing agreements with all academic partners; no individual-level data shared -- aggregates only; rare attribute suppression (unusual ritual types or phase combinations removed from datasets) |
| **Likelihood (Residual)** | Remote |
| **Impact (Residual)** | Minor |
| **Overall (Residual)** | **LOW** |
| **Risk Owner** | Product Owner |
| **Traceability** | BR-006 (REQ), FR-015, NFR-C-001 |

---

#### DPIA-009: Right to Deletion Cannot Fully Erase LLM Processing History

| Field | Assessment |
|-------|------------|
| **Risk ID** | DPIA-009 |
| **Risk Description** | Once conversation data has been processed by the LLM (AWS Bedrock/Claude), the processing has occurred and cannot be reversed. A user exercising their right to erasure can have all stored data deleted, but cannot "un-process" data that was transmitted to the LLM during active sessions. |
| **Data Categories Affected** | DR-002 (session content transmitted to LLM) |
| **Harm to Individuals** | Minimal direct harm given zero-retention DPA -- no copies retained by LLM provider. However, the user's expectation of complete erasure may not align with the technical reality that data was processed (though not stored) by a third party. This is a transparency and trust issue rather than a substantive data protection risk. |
| **Likelihood (Inherent)** | Probable |
| **Impact (Inherent)** | Minimal |
| **Overall (Inherent)** | **LOW** |
| **Mitigations** | Zero-retention DPA with AWS Bedrock -- no conversation data stored at rest (ADR-001); conversation context is session-scoped -- LLM has no persistent memory; all application-side user data deleted within 30 days of deletion request (FR-010, DR-001); transparent disclosure in privacy notice that conversations are processed by AI and subject to zero-retention agreement; clear explanation of what deletion means and does not mean |
| **Likelihood (Residual)** | Probable |
| **Impact (Residual)** | Minimal |
| **Overall (Residual)** | **LOW** |
| **Risk Owner** | Data Protection Officer (to be appointed) |
| **Traceability** | FR-010 (REQ), ADR-001, NFR-C-001 |

---

#### DPIA-010: Multi-Account Circumvention Creates Duplicate Data

| Field | Assessment |
|-------|------------|
| **Risk ID** | DPIA-010 |
| **Risk Description** | Users creating multiple accounts to bypass cooldown periods (8-hour minimum between sessions) create duplicate user profiles with fragmented data. This undermines data accuracy, complicates subject access requests, and defeats anti-dependency constraints designed to protect the user from excessive tool use. |
| **Data Categories Affected** | DR-001 (duplicate profiles), DR-002 (fragmented session history), DR-003 (incomplete ritual tracking) |
| **Harm to Individuals** | Fragmented data means ritual tracking and phase assessment are based on incomplete information, reducing clinical effectiveness. User exercising data subject rights (SAR, erasure) may not realise they have data across multiple accounts. The circumvention itself indicates the user may be forming dependency on the tool -- the anti-dependency constraint exists to protect them. |
| **Likelihood (Inherent)** | Possible |
| **Impact (Inherent)** | Minor |
| **Overall (Inherent)** | **LOW** |
| **Mitigations** | Multi-account prevention using privacy-proportionate device fingerprinting (FR-013, ADR-005); email uniqueness check at registration (email_hash uniqueness constraint in DR-001); detection heuristics for account creation patterns; user education during onboarding about why cooldowns exist (protecting recovery, not restricting access); account linking capability if duplicate detected (with user consent) |
| **Likelihood (Residual)** | Remote |
| **Impact (Residual)** | Minor |
| **Overall (Residual)** | **LOW** |
| **Risk Owner** | Development Team |
| **Traceability** | FR-013 (REQ), ADR-005, BR-002 |

### 5.3 Risk Summary

| Risk ID | Risk Title | Inherent | Residual | Status |
|---------|-----------|----------|----------|--------|
| DPIA-001 | Breach of special category health data | HIGH | MEDIUM | Open -- mitigations designed, implementation pending |
| DPIA-002 | Invalid consent from compromised executive function | HIGH | MEDIUM | Open -- consent architecture designed, validation pending |
| DPIA-003 | AI profiling creates psychological dependency | HIGH | MEDIUM | Open -- anti-dependency architecture designed, effectiveness unproven |
| DPIA-004 | LLM processes sensitive health disclosures | MEDIUM | LOW | Open -- zero-retention DPA in place |
| DPIA-005 | Inadequate crisis detection leads to harm | HIGH | MEDIUM | Open -- safety layer designed, clinical validation pending |
| DPIA-006 | Phase misassessment causes inappropriate intervention | MEDIUM | LOW | Open -- assessment protocol designed, clinical review pending |
| DPIA-007 | Ritual tracking reveals intimate behavioural patterns | MEDIUM | LOW | Open -- encryption and access controls designed |
| DPIA-008 | Research data re-identification | LOW | LOW | Open -- anonymisation framework designed |
| DPIA-009 | Right to deletion and LLM processing history | LOW | LOW | Open -- transparency approach defined |
| DPIA-010 | Multi-account circumvention creates duplicate data | LOW | LOW | Open -- prevention measures designed |

**Inherent risk profile**: 4 HIGH, 3 MEDIUM, 3 LOW
**Residual risk profile**: 0 HIGH, 4 MEDIUM, 6 LOW

All inherent HIGH risks have been reduced to MEDIUM through designed mitigations. No residual HIGH risks remain.

---

## 6. Mitigations

### 6.1 Technical Mitigations

| Mitigation | DPIA Risks Addressed | Implementation | Status |
|-----------|---------------------|----------------|--------|
| **Field-level encryption (pgcrypto)** | DPIA-001, DPIA-007 | Sensitive attributes (session transcripts, ritual names, action commitments) encrypted at column level using pgcrypto extension in PostgreSQL (ADR-006) | Designed |
| **Row Level Security (RLS)** | DPIA-001, DPIA-007 | Per-user data isolation enforced at database level. No user can access another user's data through any application pathway (ADR-006) | Designed |
| **Zero-retention DPA** | DPIA-001, DPIA-004, DPIA-009 | AWS Bedrock operates under zero-retention data processing agreement. No conversation data stored at rest by LLM provider (ADR-001) | In place |
| **Pseudonymised LLM calls** | DPIA-001, DPIA-004 | Only pseudonymised user_id transmitted to LLM. No email, name, or PII included in prompts (INT-001) | Designed |
| **TLS 1.3+ encryption in transit** | DPIA-001 | All data transmitted between user device, application layer, and data stores encrypted using TLS 1.3 or later | Designed |
| **UK data residency** | DPIA-001, DPIA-004 | All infrastructure deployed in AWS eu-west-2 (London) and Supabase UK region. No international data transfers (TC-1, ADR-008) | Designed |
| **Email hashing** | DPIA-001 | Email hashed with SHA-256 at point of collection. Raw email never stored in application database (DR-001) | Designed |
| **Automated data retention** | DPIA-001, DPIA-007 | Session data auto-deleted after 12 months. Account data purged within 30 days of deletion request. Automated enforcement prevents retention beyond policy limits (ADR-006) | Designed |
| **Defence-in-depth safety layer** | DPIA-005 | NeMo Guardrails with custom clinical filters: crisis detection, anti-warmth enforcement, diagnostic claim blocking, harmful advice prevention (ADR-003) | Designed |
| **Multi-account prevention** | DPIA-010 | Privacy-proportionate device fingerprinting, email uniqueness constraints (FR-013, ADR-005) | Designed |
| **k-anonymity for research data** | DPIA-008 | Minimum group size of 10 for any published aggregate. Rare attribute suppression. No individual-level data shared | Designed |

### 6.2 Organisational Mitigations

| Mitigation | DPIA Risks Addressed | Implementation | Status |
|-----------|---------------------|----------------|--------|
| **DPO appointment** | All | Appoint Data Protection Officer to oversee data processing, handle SARs, and provide ongoing compliance advice | Planned |
| **Clinical Advisory Board** | DPIA-003, DPIA-005, DPIA-006 | Constitute board to validate clinical protocols, review safety layer calibration, and provide annual safety sign-off | Planned |
| **Ethics Review Panel** | DPIA-002, DPIA-003 | Constitute panel to review consent architecture, assess proportionality, and monitor for unintended harms | Planned |
| **Privacy notice** | DPIA-002, DPIA-009 | Clear, accessible privacy notice explaining what data is processed, why, by whom, and for how long. Specific section on AI processing and zero-retention | Planned |
| **Data sharing agreements** | DPIA-008 | Formal agreements with all academic research partners specifying anonymisation requirements, permitted uses, and security obligations | Planned |
| **Incident response plan** | DPIA-001 | Documented breach response procedure including 72-hour ICO notification, user notification, and containment steps | Planned |
| **Staff training** | DPIA-001, DPIA-002 | Data protection training for all team members with access to user data. Specific training on vulnerable user considerations | Planned |

### 6.3 Procedural Mitigations

| Mitigation | DPIA Risks Addressed | Implementation | Status |
|-----------|---------------------|----------------|--------|
| **Consent comprehension testing** | DPIA-002 | Test consent flow with representative users (including users in acute distress) to validate comprehension | Planned |
| **Anti-dependency monitoring** | DPIA-003 | Monitor session frequency, cooldown compliance, and user attachment indicators as safety metrics. Alert Clinical Advisory Board if patterns suggest dependency formation | Planned |
| **Safety layer calibration review** | DPIA-005, DPIA-006 | Regular review of crisis detection accuracy (false positive/negative rates) and phase assessment accuracy with clinical input | Planned |
| **Annual DPIA review** | All | Full DPIA review annually or when processing changes materially (whichever is sooner) | Scheduled (2027-04-06) |
| **Ethics committee approval** | DPIA-008 | Obtain ethics committee approval before any research data collection or sharing | Planned |
| **Penetration testing** | DPIA-001 | Regular security testing of application and infrastructure, with specific focus on data exfiltration scenarios | Planned |

---

## 7. ICO Consultation

### 7.1 Prior Consultation Determination

Under UK GDPR Article 36(1), the controller must consult the ICO prior to processing where a DPIA indicates that processing would result in a high risk in the absence of measures taken by the controller to mitigate the risk, **and the controller cannot sufficiently mitigate the residual risk**.

**Residual risk assessment:**

| Risk Level | Count | Risks |
|------------|-------|-------|
| HIGH | 0 | -- |
| MEDIUM | 4 | DPIA-001, DPIA-002, DPIA-003, DPIA-005 |
| LOW | 6 | DPIA-004, DPIA-006, DPIA-007, DPIA-008, DPIA-009, DPIA-010 |

**Determination: ICO prior consultation is NOT required.**

No residual risks remain at HIGH. All inherent HIGH risks have been reduced to MEDIUM through designed mitigations. The threshold for mandatory ICO prior consultation (residual HIGH risk that cannot be sufficiently mitigated) is not met.

### 7.2 Voluntary ICO Engagement

**Recommendation: Voluntary engagement with the ICO is STRONGLY RECOMMENDED.**

Notwithstanding the formal determination above, the following factors support proactive ICO engagement:

1. **Novel processing**: Anti-dependency AI for vulnerable users has no precedent. The ICO has not previously assessed this type of processing and informal guidance would reduce regulatory uncertainty.
2. **Consent architecture innovation**: The approach to consent for users with compromised executive function (48-hour reflection periods, periodic reminders, plain language) is novel and would benefit from ICO validation.
3. **Special category data at scale**: While not "large scale" by ICO criteria, processing health data from users with mental health-adjacent conditions warrants proactive engagement.
4. **DPIA-003 (dependency risk)**: The risk that data processing itself creates the harm it is designed to prevent is philosophically novel and has implications for the ICO's understanding of AI-related risks.
5. **Regulatory goodwill**: Early, voluntary engagement demonstrates responsible innovation and builds credibility with the regulator before public launch.

**Proposed engagement**: Request informal ICO guidance session via the ICO's Innovation Hub, focusing on consent architecture for vulnerable users and the anti-dependency AI model.

---

## 8. Sign-off

| Role | Name | Signature | Date |
|------|------|-----------|------|
| **Product Owner** | Mark Craddock | PENDING | |
| **Data Protection Officer** | To be appointed | PENDING | |
| **Senior Information Risk Owner (SIRO)** | To be appointed | PENDING | |
| **Clinical Advisory Board Chair** | To be appointed | PENDING | |

**Sign-off conditions:**

1. DPO must be appointed before DPIA can be formally approved
2. Clinical Advisory Board must review and endorse DPIA-003 and DPIA-005 mitigations
3. Consent comprehension testing must be completed before DPIA-002 mitigations can be validated
4. All designed mitigations must be implemented before processing begins

---

## 9. Review and Monitoring

### 9.1 Review Schedule

| Review Type | Frequency | Next Date | Responsible |
|-------------|-----------|-----------|-------------|
| **Full DPIA review** | Annual | 2027-04-06 | DPO |
| **Risk register update** | Quarterly | 2026-07-06 | Product Owner |
| **Mitigation effectiveness review** | 6-monthly | 2026-10-06 | DPO + Product Owner |
| **Safety metrics review** | Monthly | 2026-05-06 | Clinical Advisory Board |
| **Consent comprehension audit** | Annual | 2027-04-06 | DPO |

### 9.2 Trigger Events for DPIA Update

The DPIA must be reviewed and updated before any of the following changes:

- New data categories collected or new processing purposes added
- Change in LLM provider or data processing agreement terms
- Change in data residency (any processing outside UK)
- Significant increase in user volume (e.g., exceeding 100,000 users)
- New data sharing arrangements with third parties
- Material change to anti-dependency architecture or safety layer
- Security incident or data breach affecting user data
- Change in regulatory landscape (ICO guidance, MHRA classification)
- Introduction of new features that process personal data differently

### 9.3 Metrics to Monitor

| Metric | Target | Alert Threshold | Frequency |
|--------|--------|-----------------|-----------|
| Data breach incidents | 0 | Any incident | Continuous |
| SAR response time | < 30 days | > 20 days | Per request |
| Deletion request completion | < 30 days | > 20 days | Per request |
| Consent withdrawal rate | Monitored (no target) | > 10% monthly | Monthly |
| Crisis detection false negative rate | < 1% | > 0.5% | Monthly |
| Session frequency per user (dependency indicator) | Declining over time | Increasing trend | Monthly |
| Cooldown compliance rate | > 90% | < 95% | Monthly |
| Research consent opt-in rate | Monitored (no target) | < 5% (may indicate unclear consent flow) | Monthly |

---

## 10. Traceability

### 10.1 Requirements Traceability

| DPIA Risk | Requirements | ADRs | Project Risks | Principles |
|-----------|-------------|------|---------------|------------|
| DPIA-001 | NFR-SEC-003, NFR-C-001, DR-001/002/003/004, FR-010 | ADR-001, ADR-006, ADR-008 | R-003 | PRIN-012 (Transparency) |
| DPIA-002 | NFR-C-001, NFR-U-001, DR-001 | -- | R-011 | PRIN-012 (Transparency) |
| DPIA-003 | BR-002, FR-007, FR-011, NFR-U-001 | ADR-002, ADR-008 | R-001 | PRIN-012 (Transparency) |
| DPIA-004 | INT-001, NFR-SEC-003 | ADR-001 | R-010 | -- |
| DPIA-005 | UC-4, FR-008 | ADR-003 | R-007 | -- |
| DPIA-006 | FR-003, UC-1 | ADR-007 | R-008 | -- |
| DPIA-007 | DR-003, NFR-SEC-003 | ADR-006 | R-003 | -- |
| DPIA-008 | BR-006, FR-015, NFR-C-001 | -- | -- | -- |
| DPIA-009 | FR-010, NFR-C-001 | ADR-001 | -- | PRIN-012 (Transparency) |
| DPIA-010 | FR-013, BR-002 | ADR-005 | R-009 | -- |

### 10.2 Source Documents

| Document ID | Title | Version | Relevance |
|-------------|-------|---------|-----------|
| ARC-001-REQ-v1.0 | Project Requirements | 1.0 | Data requirements (DR-001 to DR-004), functional requirements, non-functional requirements, constraints |
| ARC-001-STKE-v1.0 | Stakeholder Drivers & Goals | 1.0 | Stakeholder identification, vulnerable user analysis, consultation needs |
| ARC-001-RISK-v1.0 | Risk Register | 1.0 | Project risks (R-001 to R-015) that inform DPIA risk assessment |
| ARC-001-ADR-001-v1.0 | LLM Foundation Model Selection | 1.0 | Zero-retention DPA, UK data residency, Bedrock selection |
| ARC-001-ADR-002-v1.0 | Anti-Dependency Architecture | 1.0 | Server-side structural constraints preventing user attachment |
| ARC-001-ADR-003-v1.0 | LLM Safety Layer | 1.0 | Crisis detection, anti-warmth enforcement, clinical filters |
| ARC-001-ADR-005-v1.0 | Authentication (Supabase Auth) | 1.0 | User authentication, multi-account prevention |
| ARC-001-ADR-006-v1.0 | Data Persistence (Supabase PostgreSQL) | 1.0 | RLS, field-level encryption, UK data residency, retention automation |
| ARC-001-ADR-007-v1.0 | Phase Assessment | 1.0 | LLM-driven phase assessment protocol and validation |
| ARC-001-ADR-008-v1.0 | Deployment (AWS Fargate PWA) | 1.0 | UK data residency (eu-west-2), no push notifications |
| ARC-000-PRIN-v1.0 | Architecture Principles | 1.0 | PRIN-012 (Transparency) and other governing principles |

---

## 11. Data Subject Rights

### 11.1 Rights Implementation

| Right | UK GDPR Article | Implementation Status | Implementation Detail |
|-------|-----------------|----------------------|----------------------|
| **Right of Access (SAR)** | Art. 15 | Implemented (designed) | User can access all their data via account dashboard (FR-010). Machine-readable export capability planned. SAR response target: < 30 days. |
| **Right to Rectification** | Art. 16 | Partially implemented | Users can update profile data (DR-001). Session transcripts and ritual tracking records are immutable records of what occurred and are not subject to rectification, but users can add corrections or context. |
| **Right to Erasure** | Art. 17 | Implemented (designed) | Account deletion triggers full erasure within 30 days (FR-010, DR-001). All personal data deleted including session records, ritual tracking, and self-assessments. Anonymised research data (already aggregated) is not deleted as it is no longer personal data. |
| **Right to Data Portability** | Art. 20 | Planned | Export of all user data in structured, machine-readable format (JSON). Not yet implemented in v1.0 but included in requirements. |
| **Right to Object** | Art. 21 | Implemented (designed) | Users can withdraw consent at any time. Research consent is separate and independently withdrawable. Withdrawal stops all processing and triggers account deactivation. |
| **Right to Restrict Processing** | Art. 18 | Partially implemented | Users can stop using the tool at any time (effective restriction). Granular processing restriction (e.g., continue sessions but stop ritual tracking) is not yet implemented. |
| **Rights related to Automated Decision-Making** | Art. 22 | Not applicable | Phase assessment is AI-driven but does not produce legal or similarly significant effects that trigger Art. 22 rights. Users can continue using the tool regardless of assessed phase. No automated decisions with legal effect are made. Phase assessment is response calibration, not clinical diagnosis (ADR-004). Users are informed of the assessment and can request reassessment. |

### 11.2 Data Subject Rights Process

1. **SARs**: Users can access their data via the account dashboard. For formal SARs, requests are handled by the DPO (once appointed) within 30 days.
2. **Deletion requests**: Processed via account settings. All personal data deleted within 30 days. Confirmation sent to user.
3. **Complaints**: Users directed to the ICO if dissatisfied with data handling. ICO contact details included in privacy notice.

---

## 12. International Transfers

### 12.1 Transfer Assessment

**No international data transfers occur.**

All processing is within the United Kingdom:

| Component | Location | Justification |
|-----------|----------|---------------|
| Application hosting | AWS eu-west-2 (London) | ADR-008, TC-1 |
| LLM processing | AWS Bedrock eu-west-2 (London) | ADR-001, TC-1 |
| Database | Supabase PostgreSQL (UK region) | ADR-006, TC-1 |
| Authentication | Supabase Auth (UK region) | ADR-005, TC-1 |

### 12.2 Transfer Safeguards

No transfer safeguards (SCCs, adequacy decisions, BCRs) are required as no data leaves the UK. The UK data residency requirement (TC-1) is a non-negotiable technical constraint enforced through infrastructure selection.

**Monitoring**: Any change in provider infrastructure that could result in data processing outside the UK triggers an immediate DPIA review and potential processing suspension.

---

## 13. Children's Data

### 13.1 Assessment

**Children's data processing is out of scope for DeLimerence v1.0.**

| Control | Implementation | Reference |
|---------|---------------|-----------|
| **Age gating** | Users must confirm they are 18+ during account creation (DR-001, age_confirmed boolean) | BC-3 |
| **No child-specific content** | Tool is designed for adult users. No age-appropriate content for under-18s exists. | BC-3 |
| **Scope exclusion** | Support for minors is explicitly out of scope and would require a separate safeguarding framework, parental consent architecture, and Age Appropriate Design Code compliance | ARC-001-REQ-v1.0, Out of Scope |

### 13.2 Age Verification Limitations

The current age verification method (self-declaration) is a known limitation. A determined minor could falsely confirm they are 18+. However:

- The tool's content (CBT techniques, ERP protocols, psychoeducation about neurochemistry) is not harmful to minors who encounter it
- The anti-dependency architecture protects all users, including any minors who bypass age gating
- Crisis resources are displayed for all users regardless of age
- Future phases may implement more robust age verification if user demographics indicate minors are accessing the service

---

## 14. AI and Algorithmic Processing

### 14.1 AI Systems in Use

| AI Component | Purpose | Decision Impact | Human Oversight |
|-------------|---------|-----------------|-----------------|
| **LLM Conversational Agent** (Claude via Bedrock) | Conduct phase-aware conversations using CBT/ERP techniques and psychoeducation | Determines conversational content and intervention approach. No legal effect. | NeMo Guardrails safety layer filters all output before delivery (ADR-003). Clinical Advisory Board reviews system prompt and protocols. |
| **Phase Assessment** (LLM-driven) | Classify user's limerence phase to calibrate response strategy | Determines intervention intensity (reality-testing vs grief support). No legal effect. Phase assessment is response calibration, not diagnosis. | Structured output validation (ADR-007). Inconclusive defaults to least-harmful mode. User informed of assessment. Reassessment available. |
| **Crisis Detection** (multi-layer) | Identify indicators of suicidal ideation or self-harm | Triggers display of crisis resources. No data processing consequence -- crisis resources are always visible. | Safety-first calibration (false positives preferred). Crisis resources displayed on every screen regardless. Human crisis services provided (Samaritans, 999). |
| **Anti-Warmth Enforcement** (guardrails) | Block AI responses that simulate emotional presence or warmth-signalling language | Filters LLM output to prevent attachment-forming language. Protects user from the tool creating new dependency. | NeMo Guardrails rules with custom clinical extensions (ADR-003). Clinical Advisory Board calibration review. |

### 14.2 AI Transparency

The following transparency measures are implemented in accordance with PRIN-012:

- Tool explicitly identifies itself as software on every interaction: "This is a tool, not a therapist. It is software designed to help you understand and interrupt limerence." (FR-011)
- No persona, name, avatar, or personality is assigned to the AI. It is labelled "Tool" throughout (ADR-002)
- Users are informed that their conversations are processed by AI
- Phase assessment results are explained to users in psychoeducational terms
- The tool never claims to understand, feel, or care about the user

### 14.3 AI-Specific Data Protection Considerations

| Consideration | Assessment | Mitigation |
|--------------|------------|------------|
| **Training data** | DeLimerence does not fine-tune the LLM on user data. No user conversations contribute to model training. | Zero-retention DPA with Bedrock (ADR-001) |
| **Model bias** | LLM may have biases in understanding limerence (undertrained on this rare condition) or cultural biases in relationship norms | Clinical Advisory Board protocol review; structured output validation for phase assessment (ADR-007) |
| **Hallucination** | LLM may generate clinically inaccurate psychoeducation or inappropriate intervention advice | NeMo Guardrails safety layer (ADR-003); clinical content validated by advisory board |
| **Prompt injection** | Adversarial users may attempt to bypass anti-dependency constraints or extract system prompt | System prompt protection in safety layer (ADR-003, NFR-SEC-006); server-side constraint enforcement (ADR-002) |
| **Explainability** | Users should understand why the AI responds as it does | Phase assessment explained in plain language; intervention approach linked to psychoeducation; no opaque "black box" decisions with significant effect |

---

## 15. Summary and Action Plan

### 15.1 DPIA Summary

DeLimerence processes special category health data from psychologically vulnerable users using innovative AI technology. The DPIA has identified **10 risks** to individuals' rights and freedoms.

**Key findings:**

1. **6 of 9 ICO screening criteria are met**, making this DPIA mandatory.
2. **4 inherent HIGH risks** have been identified, all reduced to **MEDIUM** through designed mitigations.
3. **No residual HIGH risks remain**, meaning ICO prior consultation is not formally required.
4. **Voluntary ICO engagement is strongly recommended** given the novel nature of the processing.
5. The **consent architecture for vulnerable users** requires specific validation through comprehension testing with representative users.
6. The **anti-dependency architecture** is the primary mitigation for DPIA-003 (the most philosophically novel risk), but its effectiveness is unproven as no precedent exists.
7. **No international data transfers** occur -- all processing is within the UK.
8. **Children's data** is out of scope with 18+ age gating.

### 15.2 Action Plan

| # | Action | DPIA Risk | Owner | Priority | Target Date | Status |
|---|--------|-----------|-------|----------|-------------|--------|
| 1 | Appoint Data Protection Officer | All | Product Owner | CRITICAL | 2026-06-30 | Not started |
| 2 | Constitute Clinical Advisory Board | DPIA-003, DPIA-005, DPIA-006 | Product Owner | CRITICAL | 2026-06-30 | Not started |
| 3 | Constitute Ethics Review Panel | DPIA-002, DPIA-003 | Product Owner | HIGH | 2026-07-31 | Not started |
| 4 | Implement field-level encryption (pgcrypto) | DPIA-001, DPIA-007 | Development Team | HIGH | Before public beta | Not started |
| 5 | Implement Row Level Security policies | DPIA-001, DPIA-007 | Development Team | HIGH | Before public beta | Not started |
| 6 | Develop and test consent flow for vulnerable users | DPIA-002 | UX / Content Design | HIGH | Before public beta | Not started |
| 7 | Conduct consent comprehension testing | DPIA-002 | DPO + UX | HIGH | Before public beta | Not started |
| 8 | Implement NeMo Guardrails safety layer | DPIA-005, DPIA-006 | Development Team | HIGH | Before public beta | Not started |
| 9 | Implement automated data retention enforcement | DPIA-001 | Development Team | MEDIUM | Before public beta | Not started |
| 10 | Draft and publish privacy notice | DPIA-002, DPIA-009 | DPO | HIGH | Before public beta | Not started |
| 11 | Prepare data sharing agreement template | DPIA-008 | DPO | MEDIUM | Before research launch | Not started |
| 12 | Obtain ethics committee approval for research | DPIA-008 | Product Owner | MEDIUM | Before research launch | Not started |
| 13 | Develop incident response plan | DPIA-001 | DPO | HIGH | Before public beta | Not started |
| 14 | Engage ICO Innovation Hub (voluntary) | All | Product Owner + DPO | MEDIUM | 2026-09-30 | Not started |
| 15 | Implement SAR and deletion request workflow | DPIA-009 | Development Team | HIGH | Before public beta | Not started |
| 16 | Establish anti-dependency monitoring dashboard | DPIA-003 | Development Team | MEDIUM | Before public beta | Not started |
| 17 | Conduct penetration testing | DPIA-001 | Development Team | HIGH | Before public beta | Not started |
| 18 | Establish DPIA annual review process | All | DPO | LOW | 2027-03-01 | Not started |

### 15.3 Conditions for Processing

Processing of personal data **must not begin** until:

1. DPO has been appointed and has reviewed this DPIA
2. Clinical Advisory Board has been constituted and has endorsed clinical safety mitigations
3. All technical mitigations marked "Before public beta" have been implemented
4. Consent flow has been validated through comprehension testing
5. Privacy notice has been published
6. Incident response plan has been documented

---

## 16. Appendices

### Appendix A: Glossary

| Term | Definition |
|------|-----------|
| **Limerence** | Involuntary obsessive romantic attachment characterised by intrusive thoughts, compulsive rituals, and compromised executive function (Tennov, 1979) |
| **Limerent Object (LO)** | The person who is the target of limerent attachment |
| **CBT** | Cognitive Behavioural Therapy -- structured psychotherapy approach addressing unhelpful thinking patterns |
| **ERP** | Exposure and Response Prevention -- behavioural therapy technique adapted from OCD treatment protocols |
| **Phase assessment** | Classification of user's current limerence stage: initiation, crystallisation, deterioration, or resolution |
| **Ritual** | Compulsive behaviour associated with limerence (e.g., checking social media, rereading messages, engineering encounters) |
| **Anti-dependency architecture** | 9 structural constraints enforced server-side to prevent users from forming attachment to the tool |
| **Zero-retention DPA** | Data Processing Agreement under which the processor commits to not storing any data at rest |
| **RLS** | Row Level Security -- PostgreSQL feature enforcing per-user data isolation at the database level |
| **Special category data** | Data categories listed in UK GDPR Article 9, including data concerning health |
| **DLIM-5** | DeLimerence 5-item self-assessment instrument measuring limerence intensity and distress |
| **PWA** | Progressive Web App -- web application that can be installed on devices without app store distribution |

### Appendix B: Legal and Regulatory References

| Reference | Full Title | Relevance |
|-----------|-----------|-----------|
| UK GDPR Art. 5 | Principles relating to processing of personal data | Data minimisation, purpose limitation, storage limitation, integrity and confidentiality |
| UK GDPR Art. 6 | Lawfulness of processing | Art. 6(1)(a) consent as primary legal basis |
| UK GDPR Art. 9 | Processing of special categories of personal data | Health data processing requires Art. 9(2)(a) explicit consent |
| UK GDPR Art. 13-14 | Information to be provided to the data subject | Privacy notice obligations |
| UK GDPR Art. 15-22 | Rights of the data subject | Access, rectification, erasure, portability, objection, automated decision-making |
| UK GDPR Art. 25 | Data protection by design and by default | Privacy-by-design in architecture decisions |
| UK GDPR Art. 28 | Processor obligations | DPA requirements for AWS Bedrock, Supabase |
| UK GDPR Art. 32 | Security of processing | Technical and organisational measures (encryption, access control) |
| UK GDPR Art. 33-34 | Notification of breach | 72-hour ICO notification, user notification for high-risk breaches |
| UK GDPR Art. 35 | Data protection impact assessment | This document |
| UK GDPR Art. 36 | Prior consultation | ICO consultation determination (Section 7) |
| DPA 2018, Part 2, Ch. 2 | Lawful bases for processing | UK-specific implementations of GDPR bases |
| ICO DPIA Guidance | ICO guidance on conducting DPIAs | 9-criteria screening checklist, risk methodology |
| ICO AI Guidance | AI and data protection | AI-specific considerations for transparency, fairness, accountability |

### Appendix C: ICO Screening Evidence

Detailed evidence supporting the screening determination in Section 1.2, cross-referenced to project artifacts:

| Criterion | Evidence Source | Specific Reference |
|-----------|---------------|-------------------|
| 1. Evaluation/scoring | ARC-001-REQ-v1.0 | FR-003 (phase assessment), FR-004 (ritual tracking), FR-016 (self-assessment) |
| 2. Automated decisions | ARC-001-ADR-007-v1.0 | Phase determines intervention strategy (reality-testing vs grief support) |
| 3. Systematic monitoring | ARC-001-REQ-v1.0 | DR-003 (ritual tracking across sessions), DR-004 (periodic self-assessment) |
| 4. Sensitive data | ARC-001-REQ-v1.0 | DR-002, DR-003, DR-004 all classified as "special category -- health data" |
| 7. Vulnerable subjects | ARC-001-STKE-v1.0 | SD-1 (users with compromised executive function), LM12-C3 |
| 8. Innovative technology | ARC-001-ADR-002-v1.0 | Anti-dependency AI architecture with no precedent |

---

**Generated by**: ArcKit `/arckit:dpia` command
**Generated on**: 2026-04-06
**ArcKit Version**: 4.6.4-rc.1
**Project**: DeLimerence (Project 001)
**AI Model**: Claude Opus 4.6 (1M context)
**Generation Context**: DPIA from ARC-001-REQ-v1.0 (DR-001 to DR-004), ARC-001-STKE-v1.0, ARC-001-RISK-v1.0, ARC-000-PRIN-v1.0, ADR-001/002/003/005/006/007/008
