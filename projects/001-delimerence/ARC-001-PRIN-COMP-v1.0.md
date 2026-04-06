# Principles Compliance Assessment: DeLimerence

> **Template Origin**: Official | **ArcKit Version**: 4.6.4-rc.1 | **Command**: `/arckit:principles-compliance`

## Document Control

| Field | Value |
|-------|-------|
| **Document ID** | ARC-001-PRIN-COMP-v1.0 |
| **Document Type** | Principles Compliance Assessment |
| **Project** | DeLimerence (Project 001) |
| **Classification** | OFFICIAL |
| **Status** | DRAFT |
| **Version** | 1.0 |
| **Created Date** | 2026-04-06 |
| **Last Modified** | 2026-04-06 |
| **Review Cycle** | Monthly |
| **Next Review Date** | 2026-05-06 |
| **Owner** | Mark Craddock, Product Owner |
| **Reviewed By** | PENDING |
| **Approved By** | PENDING |
| **Distribution** | Project team, Clinical Advisory Board, Ethics Review Panel |
| **ArcKit Version** | 4.6.4-rc.1 |

## Revision History

| Version | Date | Author | Changes | Approved By | Approval Date |
|---------|------|--------|---------|-------------|---------------|
| 1.0 | 2026-04-06 | ArcKit AI | Initial creation from `/arckit:principles-compliance` command | PENDING | PENDING |

---

## 1. Executive Summary

### 1.1 Purpose

This document assesses the DeLimerence project (Project 001) against the 14 enterprise architecture principles defined in ARC-000-PRIN-v1.0. The assessment evaluates whether project artifacts — requirements, architectural decisions, stakeholder analysis, risk register, research, and traceability — demonstrate compliance with each principle and identifies gaps requiring remediation.

### 1.2 Assessment Context

| Field | Value |
|-------|-------|
| **Project Phase** | Discovery/Alpha |
| **Phase Description** | Requirements and ADRs created; implementation not started |
| **Principles Source** | ARC-000-PRIN-v1.0 (14 principles) |
| **Assessment Date** | 2026-04-06 |
| **Assessor** | ArcKit AI |
| **Assessment Type** | Pre-implementation compliance review |

### 1.3 Phase Implications

This assessment is conducted at Discovery/Alpha phase. Requirements and architectural decisions have been documented, but no implementation, testing, or operational evidence exists. Consequently:

- Principles with strong requirements and ADR coverage may achieve GREEN where design decisions fully address the principle
- Principles requiring implementation evidence, testing results, or operational processes cannot exceed AMBER until those artifacts exist
- No principle can achieve RED solely due to phase — RED is reserved for principles where requirements or decisions actively conflict with or fail to address the principle

### 1.4 Compliance Scorecard

| Rating | Count | Percentage | Principles |
|--------|-------|------------|------------|
| GREEN | 10 | 71% | PRIN-001, PRIN-002, PRIN-003, PRIN-004, PRIN-006, PRIN-007, PRIN-008, PRIN-010, PRIN-012, PRIN-013 |
| AMBER | 4 | 29% | PRIN-005, PRIN-009, PRIN-011, PRIN-014 |
| RED | 0 | 0% | — |
| NOT ASSESSED | 0 | 0% | — |

### 1.5 Overall Recommendation

**CONDITIONAL APPROVAL** — All 14 principles have strong requirements and architectural decision coverage. No principles are RED. Four AMBER principles require remediation before Beta gate, primarily dependent on constituting the Clinical Advisory Board and Ethics Review Panel, completing the DPIA, and implementing availability infrastructure.

---

## 2. Artifacts Reviewed

This assessment draws evidence from the following 15 project artifacts:

### 2.1 Core Governance Artifacts

| Artifact ID | Title | Version | Relevance |
|-------------|-------|---------|-----------|
| ARC-000-PRIN-v1.0 | Enterprise Architecture Principles | 1.0 | Source principles (14 principles across 6 categories) |
| ARC-001-REQ-v1.0 | Business and Technical Requirements | 1.0 | 50 requirements across 5 categories (FR, NFR, BR, INT, DR) |
| ARC-001-STKE-v1.0 | Stakeholder Analysis | 1.0 | 5 stakeholder drivers (SD-1 through SD-5), 5 goals, 4 outcomes |
| ARC-001-RISK-v1.0 | Risk Register | 1.0 | 15 risks across 6 categories |
| ARC-001-RSCH-v1.0 | Technology Research | 1.0 | Build vs buy analysis, technology evaluations |
| ARC-001-TRAC-v1.1 | Traceability Matrix | 1.1 | 76% coverage across requirements-to-design traceability |

### 2.2 Architecture Decision Records

| Artifact ID | Decision | Relevance |
|-------------|----------|-----------|
| ADR-001 | Claude via AWS Bedrock for LLM | LLM provider, UK region, DPA, safety training |
| ADR-002 | Server-side anti-dependency enforcement | Session limits, cooldown, database-backed state |
| ADR-003 | Defence-in-depth safety layer (NeMo Guardrails) | Clinical safety filters, warmth detection |
| ADR-004 | Phased regulatory launch strategy | MHRA positioning, Phase 1/Phase 2 split |
| ADR-005 | Supabase Auth with RLS | Authentication, data isolation |
| ADR-006 | Supabase PostgreSQL with field-level encryption | Data storage, encryption, retention |
| ADR-007 | Next.js for frontend | UI framework selection |
| ADR-008 | PWA on AWS Fargate (eu-west-2) | Deployment, no push notifications, UK hosting |

### 2.3 Supporting Artifacts

| Artifact ID | Title | Relevance |
|-------------|-------|-----------|
| Vendor profiles (3) | Anthropic, Supabase, AWS | DPA terms, data residency, compliance |
| Tech notes (3) | LLM safety guardrails, UK MHRA digital mental health, additional research | Regulatory and safety architecture detail |

### 2.4 Artifacts Not Yet Available

The following artifacts do not yet exist and are noted as evidence gaps where relevant:

| Expected Artifact | Impact on Assessment |
|-------------------|---------------------|
| ARC-001-DATA (Data Model) | DR-001 through DR-004 in requirements but no formal data model artifact |
| HLD / DLD (Design Documents) | No high-level or detailed design documents |
| Implementation code | No code, infrastructure, or deployed systems |
| Test results | No test evidence for any validation gate |
| DPIA | No Data Protection Impact Assessment |
| TCOP / SECD / AIPB | No compliance assessments completed |
| SOBC (Business Case) | No Strategic Outline Business Case |
| Clinical Advisory Board | Board not yet constituted |
| Ethics Review Panel | Panel not yet constituted |

---

## 3. Detailed Principle Assessments

### PRIN-001: Anti-Dependency by Design

| Field | Value |
|-------|-------|
| **Rating** | GREEN |
| **Category** | Strategic |
| **Priority** | P1 - Mandatory |
| **Statement** | All user-facing systems MUST be architecturally designed to prevent dependency formation through structural constraints enforced at infrastructure level. |

#### Evidence

| Source | Reference | Evidence |
|--------|-----------|----------|
| ARC-001-REQ-v1.0 | FR-001 | Session duration limits (server-enforced) |
| ARC-001-REQ-v1.0 | FR-002 | Cooldown periods between sessions |
| ARC-001-REQ-v1.0 | FR-006 | Action commitment gates before session continuation |
| ARC-001-REQ-v1.0 | FR-007 | Anti-warmth constraints on AI responses |
| ARC-001-REQ-v1.0 | FR-011 | Transparency statements and AI labelling |
| ARC-001-REQ-v1.0 | FR-013 | Multi-account prevention |
| ARC-001-REQ-v1.0 | NFR-U-001 | Anti-dependency UX patterns |
| ARC-001-REQ-v1.0 | BR-002 | Prevent attachment as business requirement |
| ADR-002 | Server-side enforcement | Database-backed state for session limits and cooldowns; client-side cannot circumvent |
| ADR-008 | PWA deployment | iOS PWAs cannot send push notifications — eliminates intermittent reinforcement via notifications |
| ADR-003 | Safety layer | Anti-warmth filter blocks emotional connection signalling |
| ARC-001-RISK-v1.0 | R-001 | Limerence transfer risk with 9 structural constraints documented |
| ARC-001-STKE-v1.0 | SD-2, G-4 | Product owner driver and goal explicitly prioritise anti-dependency |

#### Validation Gate Status

| Gate | Status | Evidence |
|------|--------|----------|
| Session limits enforced by backend, not frontend | DECIDED | ADR-002: Server-side enforcement with database-backed state |
| Cooldown enforcement tested for circumvention | NOT TESTED | Implementation not started; testing requires deployed system |
| AI response tone reviewed by Clinical Advisory Board | PENDING | Clinical Advisory Board not yet constituted |
| No push notifications, streaks, or engagement-reinforcing patterns | DECIDED | ADR-008: PWA chosen specifically to prevent push notifications on iOS |
| Action commitment gates present and enforced | DECIDED | FR-006 requires action gates; ADR-002 confirms server-side enforcement |

#### Assessment Rationale

GREEN despite pre-implementation phase because anti-dependency is the most thoroughly addressed principle across all artifacts. Every architectural decision has been evaluated against this principle. The choice of PWA (ADR-008) was made specifically to prevent notification-based reinforcement. Server-side enforcement (ADR-002) was chosen specifically to prevent client-side circumvention. The risk register documents 9 structural constraints against limerence transfer. All validation gates are either decided or pending on dependencies that are expected at this phase (Clinical Advisory Board, implementation).

#### Gaps

- Implementation not started — validation gates cannot be tested yet
- Clinical Advisory Board has not reviewed AI response tone (board not constituted)

---

### PRIN-002: Clinical Safety First

| Field | Value |
|-------|-------|
| **Rating** | GREEN |
| **Category** | Strategic |
| **Priority** | P1 - Mandatory |
| **Statement** | All AI-generated responses MUST pass through a multi-layer safety filter before delivery to users. No unfiltered AI output SHALL reach users under any circumstances. |

#### Evidence

| Source | Reference | Evidence |
|--------|-----------|----------|
| ARC-001-REQ-v1.0 | NFR-SEC-006 | LLM safety layer requirement (multi-layer) |
| ARC-001-REQ-v1.0 | FR-007 | Anti-warmth constraints |
| ARC-001-REQ-v1.0 | UC-4 | Crisis detection use case |
| ADR-003 | Defence-in-depth | NeMo Guardrails + custom clinical filters; safety operates independently of AI model |
| ADR-001 | Claude selection | Constitutional AI safety training as selection factor |
| ARC-001-RISK-v1.0 | R-004 | Harmful response risk with multi-layer mitigation |
| ARC-001-RISK-v1.0 | R-001 | Limerence transfer risk |
| Tech note | llm-safety-guardrails.md | Detailed safety architecture research |

#### Validation Gate Status

| Gate | Status | Evidence |
|------|--------|----------|
| Multi-layer safety filter architecture documented | DECIDED | ADR-003: Defence-in-depth with NeMo Guardrails + custom filters |
| Safety filter catch rate exceeds 99% on adversarial test suite | NOT TESTED | Implementation not started |
| Crisis detection tested against validated datasets | NOT TESTED | Implementation not started |
| Warmth detection calibrated and approved by CAB | PENDING | CAB not constituted; warmth classifier needs training data |
| Safety filter operates independently of AI model | DECIDED | ADR-003: NeMo Guardrails operates as independent middleware |
| Clinical Advisory Board signed off on safety protocols | PENDING | CAB not yet constituted |

#### Assessment Rationale

GREEN because the multi-layer safety architecture is fully designed across ADR-001 (model selection for safety), ADR-003 (independent safety layer), and requirements (NFR-SEC-006, FR-007, UC-4). The defence-in-depth approach — system prompt constraints, NeMo Guardrails middleware, and custom clinical filters — addresses the principle's core requirement that safety filters operate independently of the AI model.

#### Gaps

- Custom warmth classifier requires training data (implementation dependency)
- Clinical Advisory Board not yet constituted for safety protocol sign-off
- Adversarial test suite not yet created

---

### PRIN-003: Supplement, Not Replace

| Field | Value |
|-------|-------|
| **Rating** | GREEN |
| **Category** | Strategic |
| **Priority** | P1 - Mandatory |
| **Statement** | Systems MUST explicitly position themselves as supplements to professional therapy, never as replacements. The architecture MUST structurally prevent the system from occupying a therapist role. |

#### Evidence

| Source | Reference | Evidence |
|--------|-----------|----------|
| ARC-001-REQ-v1.0 | BR-005 | Business requirement: supplement professional support |
| ARC-001-REQ-v1.0 | FR-011 | Transparency statements including "not a therapist" messaging |
| ARC-001-REQ-v1.0 | UC-3 | Graduated intervention at session 10+ with referral pathways |
| ADR-003 | Safety layer | Blocks diagnostic claims and clinical recommendations |
| ADR-004 | Phased launch | Phase 1 psychoeducation only — deliberately below therapy threshold |
| ARC-001-STKE-v1.0 | SD-3 | Mental health professionals as key stakeholder driver |

#### Validation Gate Status

| Gate | Status | Evidence |
|------|--------|----------|
| "Not a therapist" disclaimers in onboarding and sessions | DECIDED | FR-011 requires transparency statements at defined intervals |
| No diagnostic language in response templates or prompts | DECIDED | ADR-003: Safety layer blocks diagnostic claims |
| Referral pathways documented and functional | DECIDED | UC-3 defines graduated referral at session 10+ |
| CAB confirmed tool does not cross therapy boundary | PENDING | CAB not yet constituted |
| User research confirms supplementary understanding | NOT TESTED | No user research conducted yet |

#### Assessment Rationale

GREEN because requirements, ADR decisions, and phased launch strategy consistently enforce supplementary positioning. ADR-004's Phase 1 restriction to psychoeducation is a structural constraint that prevents therapy boundary crossing. The safety layer (ADR-003) blocks diagnostic language independently of the system prompt.

#### Gaps

- Content design not started — specific disclaimer language not written
- User research to validate understanding not conducted

---

### PRIN-004: Data Residency and Sovereignty

| Field | Value |
|-------|-------|
| **Rating** | GREEN |
| **Category** | Data |
| **Priority** | P1 - Mandatory |
| **Statement** | All user data MUST be stored and processed within the United Kingdom. No user data SHALL be transferred to, processed in, or accessible from jurisdictions outside the UK without explicit regulatory approval. |

#### Evidence

| Source | Reference | Evidence |
|--------|-----------|----------|
| ARC-001-REQ-v1.0 | TC-1 | UK data residency as technical constraint |
| ARC-001-REQ-v1.0 | NFR-C-001 | UK GDPR compliance requiring UK processing |
| ADR-001 | AWS Bedrock eu-west-2 | LLM processing in UK region |
| ADR-006 | Supabase with UK hosting | Database hosted via AWS eu-west-2 |
| ADR-008 | AWS Fargate eu-west-2 | Application hosting in UK region |
| Research | Technology evaluations | All technology selections specify UK region availability |

#### Validation Gate Status

| Gate | Status | Evidence |
|------|--------|----------|
| All infrastructure confirmed UK-hosted | DECIDED | ADR-001, ADR-006, ADR-008: All specify eu-west-2 (London) |
| Third-party DPAs include UK residency clauses | DECIDED | ADR-001: Bedrock DPA; ADR-006: Supabase DPA |
| No data egress to non-UK jurisdictions | DECIDED | Architecture specifies UK-only; network review pending implementation |
| Backup and DR infrastructure UK-resident | PENDING | DR architecture not yet detailed |
| AI/ML processing confirmed UK-resident | DECIDED | ADR-001: Bedrock eu-west-2 |

#### Assessment Rationale

GREEN because every architectural decision consistently specifies UK data residency. ADR-001 (Bedrock eu-west-2), ADR-006 (Supabase via AWS eu-west-2), and ADR-008 (Fargate eu-west-2) form a complete UK-resident architecture. No decision permits non-UK processing.

#### Gaps

- Supabase UK hosting relies on their AWS infrastructure — operational verification pending
- DR/backup region not explicitly documented yet

---

### PRIN-005: Privacy by Design and Data Minimisation

| Field | Value |
|-------|-------|
| **Rating** | AMBER |
| **Category** | Data |
| **Priority** | P1 - Mandatory |
| **Statement** | Systems MUST collect only the minimum data necessary to deliver the service and MUST implement privacy controls at the architectural level, not as an afterthought. |

#### Evidence

| Source | Reference | Evidence |
|--------|-----------|----------|
| ARC-001-REQ-v1.0 | NFR-C-001 | UK GDPR compliance requirement |
| ARC-001-REQ-v1.0 | FR-010 | Consent flow requirement |
| ARC-001-REQ-v1.0 | FR-015 | Research consent with 48-hour delay (cooling-off for compromised users) |
| ARC-001-REQ-v1.0 | DR-001 | Minimal user profile: email_hash, not plaintext email |
| ADR-005 | Supabase Auth with RLS | Row-level security for data isolation between users |
| ADR-006 | Field-level encryption | pgcrypto for sensitive content fields; data retention policies |
| ARC-001-RISK-v1.0 | R-003 | GDPR breach risk |
| ARC-001-RISK-v1.0 | R-011 | Consent validity for users with compromised executive function |

#### Validation Gate Status

| Gate | Status | Evidence |
|------|--------|----------|
| Data inventory with justification for each field | PARTIAL | DR-001 through DR-004 define data categories; no formal data model artifact (ARC-001-DATA) |
| Field-level encryption implemented for sensitive content | DECIDED | ADR-006: pgcrypto for field-level encryption |
| Consent flow reviewed for compromised capacity | DECIDED (DESIGN) | FR-015: 48-hour delay; R-011 identifies risk; detailed design pending |
| Right to deletion within 30-day SLA | DECIDED | ADR-006: Retention policies defined; implementation pending |
| Retention periods defined and automated | DECIDED | ADR-006: Retention schedule in decision; automation pending |
| DPIA completed and submitted | NOT STARTED | No DPIA artifact exists |

#### Assessment Rationale

AMBER because while requirements and ADR decisions address data minimisation (email hashing, field-level encryption, RLS, retention policies), two significant gaps remain: (1) No DPIA has been completed, which is a mandatory validation gate for this principle and a legal requirement under UK GDPR Article 35 for processing special category data at scale; (2) The consent architecture for users with compromised executive function (R-011) is identified as a risk but lacks detailed design — the 48-hour cooling-off period (FR-015) is a partial solution but does not address initial consent validity.

#### Gaps

- **DPIA not completed** — Required before any processing of special category data begins
- **Consent architecture for compromised users** needs detailed design beyond the 48-hour cooling-off period
- **No formal data model artifact** — DR-001 through DR-004 exist in requirements but ARC-001-DATA has not been created

#### Remediation

| Action | Target Date | Dependency |
|--------|-------------|------------|
| Complete DPIA | 2026-10-06 | Data model must be finalised first |
| Design compromised-user consent architecture | 2026-08-06 | Clinical Advisory Board input required |
| Create ARC-001-DATA data model artifact | 2026-07-06 | None |

---

### PRIN-006: Special Category Data Protection

| Field | Value |
|-------|-------|
| **Rating** | GREEN |
| **Category** | Data |
| **Priority** | P1 - Mandatory |
| **Statement** | All health-related data MUST be encrypted at rest and in transit with field-level encryption for sensitive content. The lawful basis for processing special category data under Article 9 MUST be established and documented before any processing begins. |

#### Evidence

| Source | Reference | Evidence |
|--------|-----------|----------|
| ARC-001-REQ-v1.0 | NFR-SEC-003 | TLS 1.3+, AES-256 at rest, field-level encryption |
| ARC-001-REQ-v1.0 | DR-001 through DR-004 | All data categories classified CONFIDENTIAL/health |
| ADR-006 | pgcrypto field-level encryption | Encryption for ritual descriptions, emotional disclosures |
| ADR-006 | RLS access control | Least-privilege access via row-level security |
| ADR-005 | Supabase Auth | Authentication and authorisation architecture |
| ADR-001 | Zero-retention DPA | Bedrock DPA prevents third-party retention of health data |

#### Validation Gate Status

| Gate | Status | Evidence |
|------|--------|----------|
| AES-256 encryption at rest | DECIDED | NFR-SEC-003 and ADR-006 specify AES-256 |
| TLS 1.3+ for all data in transit | DECIDED | NFR-SEC-003 mandates TLS 1.3+ |
| Field-level encryption for sensitive fields | DECIDED | ADR-006: pgcrypto for identified sensitive fields |
| Article 9 lawful basis documented | DECIDED | Explicit consent basis identified in requirements |
| DPIA completed | NOT STARTED | Cross-reference PRIN-005 gap |
| Breach notification procedures documented | PENDING | Not yet documented |
| Least-privilege access controls | DECIDED | ADR-005/ADR-006: RLS enforces least-privilege |

#### Assessment Rationale

GREEN because the encryption and access control architecture is comprehensively designed. NFR-SEC-003, ADR-005, and ADR-006 together specify encryption at rest (AES-256), in transit (TLS 1.3+), at field level (pgcrypto), and access isolation (RLS). All data categories are classified. The DPIA gap is captured under PRIN-005 rather than duplicated here, as the encryption and protection mechanisms themselves are fully addressed.

#### Gaps

- DPIA not completed (captured in PRIN-005 remediation)
- Breach notification procedures not yet documented
- Implementation and testing not started

---

### PRIN-007: Zero-Retention Third-Party Processing

| Field | Value |
|-------|-------|
| **Rating** | GREEN |
| **Category** | Integration |
| **Priority** | P1 - Mandatory |
| **Statement** | All third-party AI/ML processing MUST operate under data processing agreements that contractually prohibit provider storage, retention, or use of user content for any purpose including model training. |

#### Evidence

| Source | Reference | Evidence |
|--------|-----------|----------|
| ARC-001-REQ-v1.0 | INT-001 | No PII to LLM; pseudonymised user IDs; DPA required |
| ADR-001 | Bedrock zero-retention | AWS Bedrock DPA includes zero-retention clause for API usage |
| ADR-001 | Anthropic GDPR DPA | Confirmed DPA covers GDPR requirements; updated January 2026 |
| Research | Vendor profiles | Anthropic DPA terms verified; Supabase DPA terms verified |
| ARC-001-REQ-v1.0 | INT-001 | Architecture designed for provider substitution |

#### Validation Gate Status

| Gate | Status | Evidence |
|------|--------|----------|
| DPA executed with every third-party processor | DECIDED | ADR-001: Bedrock DPA; vendor profiles confirm terms |
| Zero-retention clause confirmed | DECIDED | ADR-001: Bedrock zero-retention confirmed |
| No-training clause confirmed | DECIDED | ADR-001: Anthropic/Bedrock API usage excluded from training |
| Provider compliance validation documented | DECIDED | Research documents audit rights and certifications |
| Architecture supports provider substitution | DECIDED | ADR-001: Abstraction layer for LLM provider substitution |
| Audit log maintained | PENDING | Implementation not started |

#### Assessment Rationale

GREEN because this principle has the strongest evidence chain: INT-001 requires pseudonymised IDs and DPAs, ADR-001 selects Bedrock specifically for zero-retention DPA terms, research confirms Anthropic's updated January 2026 DPA, and vendor profiles document compliance terms. The architecture also supports provider substitution if terms change.

#### Gaps

- Audit logging of third-party processing transactions requires implementation
- DPA terms require periodic re-validation (process not defined)

---

### PRIN-008: Graceful Degradation

| Field | Value |
|-------|-------|
| **Rating** | GREEN |
| **Category** | Integration |
| **Priority** | P2 - Important |
| **Statement** | Systems MUST degrade gracefully when external dependencies fail, providing safe fallback content with crisis resources rather than broken interfaces or error states. |

#### Evidence

| Source | Reference | Evidence |
|--------|-----------|----------|
| ARC-001-REQ-v1.0 | NFR-A-003 | Circuit breaker pattern; 15-second timeout; static fallback with crisis resources; cooldown independent of LLM |
| ADR-001 | Fallback strategy | Static content fallback on provider outage including crisis helpline numbers |
| ADR-002 | Independent enforcement | Anti-dependency constraints (session limits, cooldowns) function independently of AI availability |
| ADR-008 | Infrastructure resilience | ALB health checks, auto-scaling groups |

#### Validation Gate Status

| Gate | Status | Evidence |
|------|--------|----------|
| Circuit breaker patterns for all external dependencies | DECIDED | NFR-A-003: Circuit breaker required |
| Static fallback includes crisis resources | DECIDED | NFR-A-003 and ADR-001: Crisis helplines in fallback |
| Fallback content reviewed by CAB | PENDING | CAB not yet constituted |
| Degraded mode tested | NOT TESTED | Implementation not started |
| Anti-dependency constraints enforced in degraded mode | DECIDED | ADR-002: Constraints operate independently |
| Cooldown timers independent of AI availability | DECIDED | NFR-A-003 and ADR-002: Cooldowns are infrastructure-level |

#### Assessment Rationale

GREEN because the graceful degradation architecture is well-specified across requirements and ADRs. The critical design decision — anti-dependency constraints operating independently of AI availability (ADR-002) — ensures that degraded mode does not compromise the core safety architecture. Static fallback content with crisis resources (NFR-A-003, ADR-001) addresses the clinical safety aspect of degradation.

#### Gaps

- Degraded mode testing requires implementation
- Clinical Advisory Board has not reviewed fallback content

---

### PRIN-009: Availability for Crisis Moments

| Field | Value |
|-------|-------|
| **Rating** | AMBER |
| **Category** | Quality Attribute |
| **Priority** | P2 - Important |
| **Statement** | User-facing systems MUST achieve minimum 99.9% availability, measured monthly. Planned maintenance MUST be scheduled outside peak distress hours. |

#### Evidence

| Source | Reference | Evidence |
|--------|-----------|----------|
| ARC-001-REQ-v1.0 | NFR-A-001 | 99.9% uptime target |
| ARC-001-REQ-v1.0 | NFR-A-002 | RPO 1 hour, RTO 4 hours |
| ADR-008 | Fargate deployment | Auto-scaling, multi-AZ capable architecture |
| ARC-001-RISK-v1.0 | R-007 | Crisis not detected risk |

#### Validation Gate Status

| Gate | Status | Evidence |
|------|--------|----------|
| 99.9% availability target documented | DECIDED | NFR-A-001 specifies target |
| Multi-region or multi-AZ deployment | DECIDED | ADR-008: Fargate with multi-AZ capability |
| Automated failover tested | NOT TESTED | No infrastructure deployed |
| Maintenance windows defined | NOT DEFINED | No operational schedule created |
| RTO tested within 15-minute target | NOT TESTED | RTO defined as 4 hours (NFR-A-002), exceeds principle's 15-minute aspiration |
| Health monitoring and alerting operational | NOT IMPLEMENTED | No monitoring infrastructure |

#### Assessment Rationale

AMBER because while the availability target and infrastructure architecture are specified, this principle has the most implementation-dependent validation gates. No DR testing evidence exists, no availability monitoring is configured, and no maintenance windows have been defined. Additionally, the documented RTO of 4 hours (NFR-A-002) exceeds the principle's 15-minute aspiration, though the principle statement focuses on the 99.9% availability target rather than RTO specifically.

#### Gaps

- **No DR testing** — Cannot validate failover or recovery procedures
- **No monitoring infrastructure** — Cannot measure or alert on availability
- **Maintenance windows not defined** — Peak distress hour scheduling not established
- **RTO gap** — NFR-A-002 specifies 4-hour RTO vs. principle's 15-minute aspiration

#### Remediation

| Action | Target Date | Dependency |
|--------|-------------|------------|
| Implement availability monitoring and alerting | 2026-09-06 | Infrastructure deployment |
| Conduct DR test and validate failover | 2026-09-06 | Infrastructure deployment |
| Define maintenance windows based on usage patterns | 2026-09-06 | Operational data |
| Review RTO gap (4hr vs 15min) with architecture team | 2026-07-06 | None |

---

### PRIN-010: Outcome Velocity Over Engagement Depth

| Field | Value |
|-------|-------|
| **Rating** | GREEN |
| **Category** | Quality Attribute |
| **Priority** | P1 - Mandatory |
| **Statement** | Success metrics MUST measure recovery velocity — how quickly users improve and disengage — not engagement depth. Declining usage MUST be treated as the primary success indicator. |

#### Evidence

| Source | Reference | Evidence |
|--------|-----------|----------|
| ARC-001-REQ-v1.0 | BR-003 | 50% ritual reduction in 90 days as success metric |
| ARC-001-REQ-v1.0 | Success metrics | Explicitly measure declining usage as positive outcome |
| ARC-001-REQ-v1.0 | Conflict C-2 | Resolution: Reframed metrics — outcome velocity, not engagement depth |
| ADR-002 | Anti-dependency constraints | Deliberately suppress engagement through session limits and cooldowns |
| ARC-001-STKE-v1.0 | Funder framing | Reframed as impact investors measuring recovery metrics, not engagement |

#### Validation Gate Status

| Gate | Status | Evidence |
|------|--------|----------|
| Recovery metrics defined | DECIDED | BR-003: Ritual reduction rate, time-to-resolution, declining session frequency |
| No engagement-depth metrics as success KPIs | DECIDED | Conflict C-2 resolution explicitly prohibits engagement metrics as success indicators |
| A/B testing evaluates recovery velocity | PENDING | No A/B testing framework implemented |
| Stakeholder dashboards present recovery metrics | PENDING | No dashboards implemented |
| CAB reviewed metrics framework | PENDING | CAB not constituted |

#### Assessment Rationale

GREEN because this principle is deeply embedded in the project philosophy from source research through requirements to architectural decisions. The Conflict C-2 resolution in requirements explicitly addresses the tension between conventional SaaS metrics and anti-dependency goals. BR-003's 50% ritual reduction target defines success as declining usage. ADR-002's session constraints deliberately suppress engagement. Stakeholder analysis reframes funders as impact investors. This is one of the most consistently addressed principles.

#### Gaps

- Analytics infrastructure not implemented
- A/B testing framework not established
- Clinical Advisory Board has not reviewed metrics framework

---

### PRIN-011: Clinical Governance for AI Behaviour

| Field | Value |
|-------|-------|
| **Rating** | AMBER |
| **Category** | Development Practices |
| **Priority** | P1 - Mandatory |
| **Statement** | All changes to AI system prompts, response protocols, safety filter rules, and therapeutic content MUST be version-controlled and MUST require Clinical Advisory Board approval before deployment to production. |

#### Evidence

| Source | Reference | Evidence |
|--------|-----------|----------|
| ARC-001-REQ-v1.0 | NFR-M-001 | System prompt version control, clinical review for every change, 15-minute rollback |
| ADR-001 | System prompt as clinical core | System prompt positioned as the clinical foundation |
| ADR-003 | Safety layer with CAB input | Safety filter rules subject to clinical review |
| ARC-001-STKE-v1.0 | SD-4 | Clinical Advisory Board identified as key stakeholder driver |

#### Validation Gate Status

| Gate | Status | Evidence |
|------|--------|----------|
| System prompts in version control | NOT STARTED | No system prompt exists yet |
| Clinical change management process documented | NOT STARTED | No process document |
| CAB approval required before production deployment | DECIDED | NFR-M-001 requires clinical review |
| Rollback tested within 15-minute target | NOT TESTED | No system to test |
| Emergency rollback authority defined | NOT DEFINED | No authority assignment |
| Clinical change log maintained | NOT STARTED | No log |

#### Assessment Rationale

AMBER because while the requirements (NFR-M-001) clearly mandate clinical governance for AI behaviour and the stakeholder analysis identifies the Clinical Advisory Board as a driver, the board itself is not yet constituted. The system prompt — described in ADR-001 as the "clinical core" — has not been written. No clinical change management process exists. This principle cannot achieve GREEN until the Clinical Advisory Board is constituted and the system prompt is under version-controlled clinical governance.

#### Gaps

- **Clinical Advisory Board not constituted** — Target: 2026-07-06
- **System prompt not written** — Cannot be version-controlled or reviewed
- **No clinical change management process** — Process needs documentation
- **Emergency rollback authority not defined** — No authority assignment

#### Remediation

| Action | Target Date | Dependency |
|--------|-------------|------------|
| Constitute Clinical Advisory Board | 2026-07-06 | Recruitment of clinical advisors |
| Write initial system prompt | 2026-08-06 | CAB input on therapeutic approach |
| Document clinical change management process | 2026-08-06 | CAB constituted |
| Define emergency rollback authority | 2026-08-06 | CAB constituted |

---

### PRIN-012: Transparent AI

| Field | Value |
|-------|-------|
| **Rating** | GREEN |
| **Category** | Development Practices |
| **Priority** | P1 - Mandatory |
| **Statement** | AI systems MUST consistently and prominently identify themselves as software tools. The system MUST NOT simulate human presence, emotional connection, or therapeutic relationship. |

#### Evidence

| Source | Reference | Evidence |
|--------|-----------|----------|
| ARC-001-REQ-v1.0 | FR-011 | AI labelled as "Tool"; transparency statements at defined intervals; periodic reminders |
| ARC-001-REQ-v1.0 | FR-007 | Anti-warmth constraints prevent simulated emotional connection |
| ADR-002 | No persona constraint | Server-side enforcement prevents persona adoption |
| ADR-003 | Safety layer | Blocks warmth-signalling and emotional language |
| Source articles | Design philosophy | "No name, no avatar, no personality" as foundational design principle |

#### Validation Gate Status

| Gate | Status | Evidence |
|------|--------|----------|
| AI identified as "Tool" in all interfaces | DECIDED | FR-011: Explicit "Tool" labelling requirement |
| No avatar, human name, or personality traits | DECIDED | FR-007, ADR-002: No persona, no avatar, no name |
| Transparency reminders at defined intervals | DECIDED | FR-011: Periodic reminder requirement |
| Response style reviewed for warmth/attachment risk | PENDING | CAB not constituted; no responses to review |
| No typing indicators or presence signals | DECIDED | ADR-002: No presence simulation |
| User testing confirms software understanding | NOT TESTED | No user research conducted |

#### Assessment Rationale

GREEN because transparency is one of the most consistently enforced principles, addressed from source research ("no name, no avatar, no personality") through requirements (FR-011, FR-007) to architectural decisions (ADR-002 server-side enforcement, ADR-003 warmth blocking). The combination of explicit "Tool" labelling, anti-warmth filters, and no persona constraints creates multiple reinforcing layers.

#### Gaps

- No user testing to confirm users understand they are interacting with software
- CAB has not reviewed response style

---

### PRIN-013: Regulatory Engagement Before Feature Launch

| Field | Value |
|-------|-------|
| **Rating** | GREEN |
| **Category** | Regulatory and Compliance |
| **Priority** | P1 - Mandatory |
| **Statement** | Features that may cross regulatory boundaries MUST be assessed against applicable regulatory frameworks before deployment. No feature SHALL be launched that could trigger medical device classification without prior regulatory assessment. |

#### Evidence

| Source | Reference | Evidence |
|--------|-----------|----------|
| ARC-001-REQ-v1.0 | NFR-C-003 | MHRA positioning assessment required |
| ARC-001-REQ-v1.0 | BR-004 | Regulatory compliance before launch as business requirement |
| ADR-004 | Phased launch strategy | Phase 1: psychoeducation only (below MHRA device threshold); Phase 2: CBT/ERP after MHRA clarity |
| ARC-001-REQ-v1.0 | Conflict C-1 | Accessibility vs clinical safety resolved via phased approach |
| ARC-001-RISK-v1.0 | R-002 | MHRA classification — highest residual risk score (16) in register |
| Tech note | uk-mhra-digital-mental-health.md | Detailed MHRA regulatory landscape analysis |

#### Validation Gate Status

| Gate | Status | Evidence |
|------|--------|----------|
| Regulatory boundary assessment for each feature | DECIDED | ADR-004: Phase 1/Phase 2 boundary explicitly mapped to MHRA thresholds |
| MHRA pre-submission engagement planned | DECIDED | ADR-004: Pre-submission engagement in Phase 2 plan |
| Phased launch approach maintained | DECIDED | ADR-004: Structural enforcement via phased feature gates |
| Legal review for efficacy claims | PENDING | No content to review yet |
| Marketing content reviewed for medical claims | PENDING | No marketing content exists |
| Assessments documented and traceable | DECIDED | ADR-004, R-002, tech note: comprehensive documentation |

#### Assessment Rationale

GREEN because the regulatory strategy is the most thoroughly documented aspect of the project. ADR-004 establishes a phased launch where Phase 1 (psychoeducation) deliberately operates below the MHRA medical device threshold, with Phase 2 (personalised CBT/ERP interventions) gated on MHRA pre-submission engagement. R-002 documents MHRA classification as the highest residual risk (score 16) with explicit mitigations. The dedicated tech note provides detailed MHRA regulatory landscape analysis. Conflict C-1 resolution demonstrates that regulatory considerations actively shape feature decisions.

#### Gaps

- MHRA pre-submission engagement not yet initiated (Phase 2 dependency)
- Legal review of content pending (no content exists yet)

---

### PRIN-014: Responsible Dual-Use Disclosure

| Field | Value |
|-------|-------|
| **Rating** | AMBER |
| **Category** | Regulatory and Compliance |
| **Priority** | P2 - Important |
| **Statement** | Knowledge and research that enables both defensive and offensive applications MUST be published within a responsible disclosure framework with ethics review before release. |

#### Evidence

| Source | Reference | Evidence |
|--------|-----------|----------|
| ARC-001-STKE-v1.0 | SD-5 | Ethics Review Panel identified as key stakeholder driver |
| ARC-001-STKE-v1.0 | SD-2 | Product owner driver includes responsible disclosure framing |
| ARC-001-RISK-v1.0 | R-005 | Publication backlash on exploitation analysis (residual risk: 12, Medium) |
| Source articles | Parts 3-5 | Explicitly address dual-use problem of limerence weaponisation knowledge |
| ARC-001-REQ-v1.0 | Conflict analysis | Trade-off between awareness and enabling explicitly acknowledged |

#### Validation Gate Status

| Gate | Status | Evidence |
|------|--------|----------|
| Ethics Review Panel reviewed and approved publication | NOT STARTED | Panel not constituted |
| Safeguarding organisations pre-briefed | NOT STARTED | No pre-briefing plan defined |
| Content framed defensively | PARTIAL | Source articles frame defensively; formal framework not documented |
| Defensive measures in place before disclosure | PENDING | Implementation not started |
| Responsible disclosure timeline followed | NOT DEFINED | No timeline established |
| Internal research classified and access-controlled | PARTIAL | Source articles published; internal research classification not formalised |

#### Assessment Rationale

AMBER because while the stakeholder analysis identifies the Ethics Review Panel and the risk register documents dual-use publication risk (R-005), the panel itself is not constituted and no formal responsible disclosure framework exists. The source articles already discuss dual-use concerns (Parts 3-5 on weaponisation), but there is no structured process for evaluating future publications against responsible disclosure criteria. Pre-briefing plans for safeguarding organisations (NCA, NCSC, IWF) are not defined.

#### Gaps

- **Ethics Review Panel not constituted** — Target: 2026-07-06
- **No formal responsible disclosure framework** — Document needs creation
- **Pre-briefing plan for safeguarding organisations not defined** — NCA, NCSC, IWF engagement plan needed
- **Internal research classification not formalised** — Access controls for offensive technique documentation

#### Remediation

| Action | Target Date | Dependency |
|--------|-------------|------------|
| Constitute Ethics Review Panel | 2026-07-06 | Recruitment of ethics advisors |
| Create responsible disclosure framework document | 2026-08-06 | Ethics Review Panel input |
| Define safeguarding organisation pre-briefing plan | 2026-08-06 | Ethics Review Panel input |
| Formalise internal research classification | 2026-07-06 | None |

---

## 4. Gap Analysis Summary

### 4.1 AMBER Principles — Consolidated Gaps

| Principle | Rating | Primary Gap | Root Cause | Severity |
|-----------|--------|-------------|------------|----------|
| PRIN-005: Privacy by Design | AMBER | DPIA not completed; consent architecture for compromised users needs design | Pre-implementation phase; Clinical Advisory Board not constituted | High — DPIA is a legal requirement before processing begins |
| PRIN-009: Availability for Crisis | AMBER | No DR testing; no monitoring; maintenance windows not defined | Pre-implementation phase — no infrastructure to test or monitor | Medium — Addressable during implementation phase |
| PRIN-011: Clinical Governance | AMBER | Clinical Advisory Board not constituted; system prompt not written | Recruitment dependency; sequencing dependency (CAB before prompt) | High — CAB is a prerequisite for multiple downstream activities |
| PRIN-014: Responsible Dual-Use | AMBER | Ethics Review Panel not constituted; no formal disclosure framework | Recruitment dependency; framework needs panel input | Medium — Urgency increases before any publication activity |

### 4.2 Cross-Cutting Dependencies

The following dependencies affect multiple AMBER principles:

| Dependency | Affects | Target Date | Impact if Delayed |
|------------|---------|-------------|-------------------|
| **Clinical Advisory Board constitution** | PRIN-005, PRIN-011 (and supports GREEN ratings for PRIN-001, PRIN-002, PRIN-003, PRIN-008, PRIN-010, PRIN-012) | 2026-07-06 | Blocks system prompt development, clinical review processes, consent design, and safety protocol sign-off |
| **Ethics Review Panel constitution** | PRIN-014 | 2026-07-06 | Blocks responsible disclosure framework and safeguarding pre-briefing |
| **Infrastructure deployment** | PRIN-009 | 2026-09-06 | Blocks DR testing, availability monitoring, and maintenance scheduling |
| **DPIA completion** | PRIN-005 | 2026-10-06 | Legal requirement before processing special category data |

### 4.3 Artifacts Not Yet Created

| Missing Artifact | Principles Affected | Priority |
|------------------|---------------------|----------|
| ARC-001-DATA (Data Model) | PRIN-005, PRIN-006 | High — Required before DPIA |
| DPIA | PRIN-005, PRIN-006 | High — Legal requirement |
| System prompt | PRIN-011, PRIN-002, PRIN-012 | High — Clinical core of the product |
| Responsible disclosure framework | PRIN-014 | Medium — Required before publication |
| DR/BCP plan | PRIN-009 | Medium — Required before production |

---

## 5. Exception Register

No exceptions have been requested or granted against any principle.

| Exception ID | Principle | Deviation | Justification | Duration | Compensating Controls | Approved By | Status |
|-------------|-----------|-----------|---------------|----------|----------------------|-------------|--------|
| — | — | — | — | — | — | — | No exceptions registered |

---

## 6. Priority Actions

The following actions are required to remediate AMBER principles, ordered by dependency and impact:

### 6.1 Immediate Priority (Target: 2026-07-06)

| # | Action | Addresses | Dependencies |
|---|--------|-----------|--------------|
| 1 | **Constitute Clinical Advisory Board** | PRIN-011 (primary); supports PRIN-002, PRIN-005, PRIN-001, PRIN-003, PRIN-008, PRIN-010, PRIN-012 | Recruitment of clinical advisors with limerence/OCD expertise |
| 2 | **Constitute Ethics Review Panel** | PRIN-014 (primary) | Recruitment of ethics advisors with dual-use research experience |
| 3 | **Create ARC-001-DATA data model artifact** | PRIN-005, PRIN-006 | None |
| 4 | **Formalise internal research classification** | PRIN-014 | None |

### 6.2 Near-Term Priority (Target: 2026-08-06)

| # | Action | Addresses | Dependencies |
|---|--------|-----------|--------------|
| 5 | **Write initial system prompt** | PRIN-011, PRIN-002, PRIN-012 | CAB constituted |
| 6 | **Document clinical change management process** | PRIN-011 | CAB constituted |
| 7 | **Design compromised-user consent architecture** | PRIN-005 | CAB input |
| 8 | **Create responsible disclosure framework** | PRIN-014 | Ethics Review Panel constituted |
| 9 | **Define safeguarding pre-briefing plan** | PRIN-014 | Ethics Review Panel constituted |

### 6.3 Implementation Phase (Target: 2026-09-06)

| # | Action | Addresses | Dependencies |
|---|--------|-----------|--------------|
| 10 | **Implement availability monitoring and alerting** | PRIN-009 | Infrastructure deployed |
| 11 | **Conduct DR test and validate failover** | PRIN-009 | Infrastructure deployed |
| 12 | **Define maintenance windows** | PRIN-009 | Usage data available |
| 13 | **Review RTO gap (4hr vs 15min)** | PRIN-009 | Architecture team |

### 6.4 Pre-Launch (Target: 2026-10-06)

| # | Action | Addresses | Dependencies |
|---|--------|-----------|--------------|
| 14 | **Complete DPIA** | PRIN-005, PRIN-006 | Data model finalised; CAB input |

---

## 7. Compliance Trend

This is the first principles compliance assessment for the DeLimerence project. Future assessments will track trend data.

| Assessment Date | GREEN | AMBER | RED | NOT ASSESSED | Overall |
|-----------------|-------|-------|-----|--------------|---------|
| 2026-04-06 (this assessment) | 10 (71%) | 4 (29%) | 0 (0%) | 0 (0%) | CONDITIONAL APPROVAL |

### 7.1 Expected Trajectory

| Milestone | Expected Change |
|-----------|----------------|
| CAB + Ethics Panel constituted (2026-07-06) | PRIN-011 and PRIN-014 move toward GREEN |
| Infrastructure deployed (2026-09-06) | PRIN-009 moves toward GREEN |
| DPIA completed (2026-10-06) | PRIN-005 moves toward GREEN |
| Beta gate assessment (target 2026-10-06) | Target: 14/14 GREEN for Beta gate approval |

---

## 8. Approvals

| Role | Name | Signature | Date |
|------|------|-----------|------|
| **Product Owner** | Mark Craddock | PENDING | PENDING |
| **Architecture Lead** | PENDING | PENDING | PENDING |
| **Clinical Advisory Board Chair** | NOT CONSTITUTED | — | — |
| **Ethics Review Panel Chair** | NOT CONSTITUTED | — | — |

---

**Generated by**: ArcKit `/arckit:principles-compliance` command
**Generated on**: 2026-04-06
**ArcKit Version**: 4.6.4-rc.1
**Project**: DeLimerence (Project 001)
**AI Model**: Claude Opus 4.6 (1M context)
**Generation Context**: Compliance assessment of 14 principles from ARC-000-PRIN-v1.0 against 15 project artifacts (REQ, STKE, RISK, RSCH, TRAC, 8 ADRs)
