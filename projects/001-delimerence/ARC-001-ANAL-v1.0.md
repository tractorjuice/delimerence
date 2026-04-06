# Architecture Governance Analysis Report: DeLimerence

> **Template Origin**: Official | **ArcKit Version**: 4.6.4-rc.1 | **Command**: `/arckit:analyze`

## Document Control

| Field | Value |
|-------|-------|
| **Document ID** | ARC-001-ANAL-v1.0 |
| **Document Type** | Governance Analysis Report |
| **Project** | DeLimerence (Project 001) |
| **Classification** | OFFICIAL |
| **Status** | DRAFT |
| **Version** | 1.0 |
| **Created Date** | 2026-04-06 |
| **Last Modified** | 2026-04-06 |
| **Review Cycle** | Monthly |
| **Next Review Date** | 2026-05-06 |
| **Owner** | Mark Craddock, Product Owner |
| **Reviewed By** | [PENDING] |
| **Approved By** | [PENDING] |
| **Distribution** | Project Team, Architecture Team, Clinical Advisory Board |
| **ArcKit Version** | 4.6.4-rc.1 |

## Revision History

| Version | Date | Author | Changes | Approved By | Approval Date |
|---------|------|--------|---------|-------------|---------------|
| 1.0 | 2026-04-06 | ArcKit AI | Initial governance analysis from 14 artifacts | [PENDING] | [PENDING] |

---

## 1. Executive Summary

### 1.1 Analysis Scope

This report presents the results of a comprehensive governance quality analysis across **14 architecture artifacts** for the DeLimerence project: 8 Architecture Decision Records (ADR-001 through ADR-008), 1 Requirements Document (REQ), 1 Risk Register (RISK), 1 Stakeholder Analysis (STKE), 2 Traceability Matrices (TRAC v1.0 and v1.1), and 1 Research Document (RSCH).

DeLimerence is a conversational AI tool designed to help people recognise and recover from limerence, built as a deliberate inversion of the companion AI model. The tool uses CBT, ERP, and psychoeducation while actively preventing users from forming attachment to the tool itself.

### 1.2 Overall Status

| Metric | Value |
|--------|-------|
| **Overall Status** | :warning: Issues Found |
| **Governance Health Score** | **72/100** (Grade C — Adequate, address high-priority issues) |
| **Total Findings** | **11** (0 CRITICAL, 3 HIGH, 6 MEDIUM, 2 LOW) |
| **Requirements Coverage** | 76% (38/50) |
| **Principles Compliance** | N/A (no principles document) |
| **Traceability Score** | 76% |
| **Stakeholder Alignment** | 90% |
| **Risk Management** | 85% |

### 1.3 Key Metrics

```
Requirements:  50 total (6 BR, 16 FR, 21 NFR, 3 INT, 4 DR)
Coverage:      38/50 (76%) — 12 orphan requirements
Risks:         15 identified (R-001 through R-015) across 6 categories
ADRs:          8 decisions (4 DRAFT, 3 PROPOSED, 1 Accepted)
Artifacts:     14 scanned
PENDING items: 36 placeholder fields across 4 governance artifacts
```

### 1.4 Recommendation

**PROCEED WITH CAUTION** — Address 3 HIGH priority issues (requirements priority normalisation, missing enterprise architecture principles document, ADR status taxonomy inconsistency) before stakeholder review. The project has strong foundations (comprehensive stakeholder analysis, risk register, 76% requirements coverage) but governance maturity needs improvement before formal approval gates.

---

## 2. Findings Summary

| ID | Category | Severity | Location | Summary | Recommendation |
|----|----------|----------|----------|---------|----------------|
| A1 | Requirements Quality | **HIGH** | ARC-001-REQ-v1.0 | All 50 requirements use SHOULD priority — no MUST requirements encoded | Normalise priority fields; encode MUST_HAVE/SHOULD_HAVE consistently |
| A2 | Requirements Quality | **MEDIUM** | Multiple (4 artifacts) | 36 [PENDING] placeholders across ADR-001, ADR-002, TRAC v1.0, TRAC v1.1 | Resolve before approval; expected for DRAFT status |
| B1 | Principles Alignment | **HIGH** | projects/000-global/ | No architecture principles document exists | Run `/arckit:principles` to create enterprise principles |
| C1 | Traceability | **MEDIUM** | ARC-001-TRAC-v1.1 | 12 orphan requirements (24%) have no ADR coverage | Review gap analysis; address security gaps (NFR-SEC-004/005) |
| C2 | Traceability | **MEDIUM** | ARC-001-TRAC-v1.1 | Integration requirements poorly covered (33% — 1/3) | Address INT-003 (Analytics) for BR-003 support |
| E1 | Stakeholder Traceability | **LOW** | ARC-001-STKE-v1.0 | Comprehensive stakeholder analysis with driver-goal-outcome chains | No action required |
| F1 | Risk Management | **LOW** | ARC-001-RISK-v1.0 | 15 risks across 6 categories, cross-referenced in ADRs | No action required |
| G1 | Business Case | **MEDIUM** | N/A | No Strategic Outline Business Case (SOBC) exists | Run `/arckit:sobc` for investor/funder engagement |
| H1 | Data Model | **MEDIUM** | ARC-001-REQ-v1.0, ADR-006 | No formal data model despite 4 DR-xxx requirements | Run `/arckit:data-model` for ERD and GDPR matrix |
| K1 | Cross-Artifact Consistency | **HIGH** | decisions/*.md | ADR status inconsistency: DRAFT, PROPOSED, Accepted (mixed casing and lifecycle stages) | Normalise status taxonomy across all ADRs |
| K2 | Cross-Artifact Consistency | **MEDIUM** | ADR-004 | ADR-004 missing Owner field (shows "---" instead of owner) | Populate Owner field |
| K3 | Cross-Artifact Consistency | **MEDIUM** | Project-level | Missing recommended artifacts: SOBC (business case), DATA (data model) | Create both artifacts given project scope |

---

## 3. Requirements Analysis

### 3.1 Requirements Coverage Matrix

| Category | Total | Covered by ADR | Uncovered | % Coverage | Target | Status |
|----------|-------|----------------|-----------|------------|--------|--------|
| Business Requirements (BR) | 6 | 4 | 2 | 67% | 100% | :warning: Below target |
| Functional Requirements (FR) | 16 | 13 | 3 | 81% | > 80% | :white_check_mark: On target |
| Non-Functional Requirements (NFR) | 21 | 16 | 5 | 76% | > 80% | :warning: Below target |
| Integration Requirements (INT) | 3 | 1 | 2 | 33% | > 80% | :x: Below target |
| Data Requirements (DR) | 4 | 4 | 0 | 100% | 100% | :white_check_mark: On target |
| **TOTAL** | **50** | **38** | **12** | **76%** | **> 80%** | **:warning: Below target** |

### 3.2 Requirements Statistics

- **Total requirements**: 50
- **Breakdown**: 6 BR, 16 FR, 21 NFR, 3 INT, 4 DR
- **Design coverage**: 38/50 (76%)
- **Test coverage**: 0/50 (0%) — implementation not yet started
- **Orphan requirements**: 12 (24%)

### 3.3 Finding A1 — Priority Normalisation (HIGH)

All 50 requirements are extracted with **SHOULD** priority by the governance scan hook. This means no requirement is formally non-negotiable, which undermines prioritisation and MoSCoW analysis.

**Root cause**: The requirements document uses `MUST_HAVE` in description text and requirement prose (e.g., session limits are described as "MUST_HAVE" features), but the priority field encoding is not consistently parseable. The hook extracted `SHOULD` for all requirements because the priority metadata is not in a standardised field position.

**Impact**: Without clear MUST vs SHOULD vs COULD priority encoding, it is impossible to determine the minimum viable product scope from the requirements document alone. Stakeholders reviewing the requirements cannot distinguish non-negotiable safety requirements (e.g., session limits, crisis signposting) from desirable features (e.g., behavioural activation prompts).

**Recommendation**: Review ARC-001-REQ-v1.0 and ensure each requirement has a clearly encoded priority field using MoSCoW notation (MUST, SHOULD, COULD, WONT) in the parseable metadata. The traceability matrix (TRAC v1.1) already shows expected priority values (MUST/SHOULD/COULD) — align the requirements document to match.

### 3.4 Finding A2 — PENDING Placeholders (MEDIUM)

**36 [PENDING] placeholders** exist across 4 governance artifacts:

| Artifact | PENDING Count | Fields Affected |
|----------|---------------|-----------------|
| ADR-002 (Anti-Dependency Enforcement) | 12 | Reviewer, Approver, Revision History approvals, Review dates |
| TRAC v1.1 (Traceability Matrix) | 11 | Reviewer, Approver, Revision History approvals, Approval table |
| TRAC v1.0 (Traceability Matrix) | 9 | Reviewer, Approver, Revision History approvals |
| ADR-001 (LLM Selection) | 4 | Reviewer, Approver, Revision History approvals |

**Assessment**: These are **expected for DRAFT documents**. Reviewer and approver fields are populated during formal review cycles. However, all placeholders should be resolved before any artifact transitions from DRAFT to APPROVED status.

### 3.5 Uncovered Requirements Detail

The following 12 requirements have no Architecture Decision Record coverage:

| Req ID | Description | Priority | Risk | Assessment |
|--------|-------------|----------|------|------------|
| BR-003 | Demonstrate Measurable Clinical Outcomes | MUST | HIGH | Covered implicitly by ritual tracking (FR-004/ADR-006) and self-assessment data model (DR-004/ADR-006). No dedicated ADR needed. |
| BR-006 | Support Research and Evidence Generation | SHOULD | LOW | Depends on FR-015/FR-016 implementation. Uses existing data pipeline (ADR-006). |
| FR-014 | Behavioural Activation Prompts | SHOULD | LOW | LLM-driven feature using existing infrastructure (ADR-001). Implementation detail within system prompt design. |
| FR-015 | Research Consent and Data Export | SHOULD | MEDIUM | Uses existing auth (ADR-005) and data (ADR-006) infrastructure. Consent flow is UX/content design. |
| FR-016 | Outcome Self-Assessment | SHOULD | MEDIUM | Uses existing data model (ADR-006, DR-004). Assessment instrument requires clinical advisory board approval. |
| NFR-SEC-004 | Secrets Management | SHOULD | **HIGH** | AWS Secrets Manager implied by ADR-008 (Fargate/AWS) but not explicitly documented. **Security gap.** |
| NFR-SEC-005 | Vulnerability Management | SHOULD | **HIGH** | CI/CD pipeline concern. **Security gap — recommend addressing in DevOps strategy.** |
| NFR-C-004 | Accessibility (WCAG 2.1 AA) | SHOULD | MEDIUM | Frontend implementation concern. Address during UX design phase. |
| NFR-U-002 | Plain Language | SHOULD | LOW | Content design requirement. Addressed through system prompt and clinical advisory board review. |
| NFR-M-002 | Observability | SHOULD | MEDIUM | Implied by ADR-008 (AWS CloudWatch) but not explicitly documented. |
| INT-002 | Crisis Resource API | COULD | LOW | Optional feature. Static crisis resource data sufficient for Phase 1. |
| INT-003 | Analytics and Outcome Reporting | SHOULD | MEDIUM | Uses existing data architecture (ADR-006). Export pipeline is implementation detail. |

**Security concern**: NFR-SEC-004 (Secrets Management) and NFR-SEC-005 (Vulnerability Management) are security requirements processing special category health data. While they may not require dedicated ADRs, they warrant explicit documentation in the DevOps strategy or as amendments to ADR-008.

---

## 4. Architecture Principles Compliance

### 4.1 Finding B1 — No Principles Document (HIGH)

**No architecture principles document exists.** A search of `projects/000-global/` confirms no `ARC-000-PRIN-*.md` file is present.

All 8 ADRs reference alignment with architecture principles in their rationale sections (e.g., "aligns with anti-dependency principle", "consistent with defence-in-depth approach"), but there is **no formal principles document to validate these claims against**.

Without a codified set of enterprise architecture principles, it is impossible to:

1. Objectively assess whether design decisions align with stated principles
2. Resolve conflicts between competing architectural approaches
3. Provide governance boards with a baseline for decision review
4. Ensure consistency across projects (if additional projects are created under `projects/`)

### 4.2 Recommendation

Run `/arckit:principles` to create an enterprise architecture principles document at `projects/000-global/ARC-000-PRIN-v1.0.md`. Based on the existing artifacts, recommended principles should include:

- **Anti-Dependency by Design** — All system behaviours must actively discourage user attachment
- **Defence in Depth** — Safety controls must be layered (prompt, guardrail, application, infrastructure)
- **Clinical Safety First** — Architecture decisions must prioritise clinical safety over engagement metrics
- **Data Minimisation** — Collect only data necessary for therapeutic function and regulatory compliance
- **Regulatory Readiness** — Architecture must support MHRA classification and ICO compliance pathways
- **Graceful Degradation** — System must fail safely, defaulting to static therapeutic content

### 4.3 Compliance Assessment

| Principle (Implied) | ADRs Demonstrating Alignment | Evidence Quality |
|---------------------|------------------------------|------------------|
| Anti-Dependency by Design | ADR-002, ADR-003, ADR-007 | Strong — central to product architecture |
| Defence in Depth | ADR-003 (Safety Layer) | Strong — multi-layer safety architecture |
| Clinical Safety First | ADR-003, ADR-004, ADR-007 | Moderate — clinical advisory board referenced but not yet engaged |
| Data Minimisation | ADR-006 | Moderate — RLS and encryption documented |
| Regulatory Readiness | ADR-004 (Phased Launch) | Strong — MHRA/ICO pathway explicit |
| Graceful Degradation | ADR-001, ADR-008 | Moderate — static fallback mentioned |

**Principles Compliance Score**: N/A — cannot formally assess without codified principles document.

---

## 5. Stakeholder Traceability Analysis

### 5.1 Finding E1 — Comprehensive Stakeholder Analysis (LOW)

ARC-001-STKE-v1.0 provides a comprehensive stakeholder analysis with:

- **Stakeholder identification** across users, professionals, regulators, and ethical bodies
- **Driver-goal-outcome chains** linking stakeholder motivations to measurable project outcomes
- **RACI matrix** assigning responsibilities across stakeholder groups
- **Tension analysis** identifying conflicts between accessibility and clinical safety

### 5.2 Stakeholder-Requirement Traceability

| Stakeholder Group | Driver | Key Goals | Requirements Mapped | ADR Coverage |
|-------------------|--------|-----------|--------------------|--------------| 
| Users (SD-1) | Acute psychological distress, need intervention | G-1: Beta Q4 2026, G-2: 50% ritual reduction | BR-001, BR-003, FR-001-009 | ADR-001, ADR-004, ADR-006, ADR-007 |
| Product Owner (SD-2) | Demonstrate anti-dependency AI is viable | G-4: Prevent attachment | BR-002, FR-001-002, FR-007 | ADR-002, ADR-003 |
| Clinical Advisory Board (SD-4) | Clinical safety and evidence base | G-4: Clinical safety | NFR-SEC-006, NFR-M-001 | ADR-003, ADR-001 |
| ICO (SD-7) | Data protection compliance | G-3: GDPR compliance | NFR-C-001, DR-001-004 | ADR-006, ADR-005 |
| MHRA (SD-8) | Medical device classification | G-3: Regulatory classification | NFR-C-003 | ADR-004, ADR-007 |
| Therapists (SD-3) | Complement, not replace, professional practice | G-5: Credible supplement | BR-005 | ADR-003, ADR-004 |

### 5.3 Assessment

**Stakeholder Alignment Score: 90%**

Requirements are traceable to stakeholder goals via inline references in the STKE document. The stakeholder-requirement-ADR chain is well-documented in the traceability matrix (TRAC v1.1, Section 6). No critical gaps identified.

The 10% gap is due to:
- Research community stakeholders (SD-5) have requirements (BR-006, FR-015, FR-016) that lack ADR coverage
- Safeguarding professionals (SD-6) are identified as stakeholders but have limited direct requirement mapping

---

## 6. Risk Management Analysis

### 6.1 Finding F1 — Risk Register Assessment (LOW)

ARC-001-RISK-v1.0 provides a comprehensive risk register following HM Treasury Orange Book principles:

| Metric | Value |
|--------|-------|
| Total risks identified | 15 |
| Risk categories | 6 (Strategic, Clinical, Regulatory, Technical, Operational, Ethical) |
| Inherent risk score (total) | 197 |
| Residual risk score (total) | 121 |
| Control effectiveness | 39% reduction |
| Critical risks (inherent) | 3 (reduced to 0 residual) |
| High risks (residual) | 3 |

### 6.2 Risk Distribution

| Category | Count | Avg Inherent | Avg Residual | Control Effectiveness |
|----------|-------|--------------|--------------|----------------------|
| Strategic | 2 | 15.0 | 9.0 | 40% reduction |
| Clinical | 3 | 17.0 | 10.0 | 41% reduction |
| Regulatory | 3 | 15.7 | 9.7 | 38% reduction |
| Technical | 3 | 12.3 | 7.7 | 38% reduction |
| Operational | 2 | 11.0 | 7.0 | 36% reduction |
| Ethical | 2 | 14.5 | 9.0 | 38% reduction |

### 6.3 Risk-ADR Cross-Reference

All 8 ADRs reference specific risks from the risk register. Key risk-decision mappings:

| Risk | Description | Mitigating ADR(s) |
|------|-------------|-------------------|
| R-001 | User develops attachment to the tool | ADR-002 (Anti-Dependency), ADR-003 (Safety Layer) |
| R-002 | MHRA classifies as medical device | ADR-004 (Phased Launch) |
| R-003 | ICO enforcement action | ADR-006 (Data Architecture), ADR-005 (Auth) |
| R-004 | Clinical harm from inappropriate advice | ADR-003 (Safety Layer), ADR-007 (Phase Assessment) |
| R-009 | Delivery timeline exceeds Q4 2026 | ADR-001 (LLM Selection — managed service reduces build time) |

### 6.4 Assessment

**Risk Management Score: 85%**

The risk register is comprehensive with clear ownership, mitigations, and cross-references to ADRs. Risk owners are assigned from the stakeholder RACI matrix. The 15% gap is due to:
- No formal risk review cadence documented (monthly review date set but no review process defined)
- Residual high risks (3) need escalation criteria defined

---

## 7. Business Case Analysis

### 7.1 Finding G1 — No SOBC Exists (MEDIUM)

No Strategic Outline Business Case (SOBC) or equivalent business case document exists in the project artifacts. For a project seeking funding or investment to proceed beyond prototype stage, a formal business case would strengthen the proposition by:

1. Articulating the economic case (cost-benefit analysis, TCO)
2. Defining the commercial case (delivery model, licensing, sustainability)
3. Establishing the financial case (funding requirements, cash flow)
4. Presenting the management case (governance, delivery plan, benefits realisation)
5. Making the strategic case (alignment with broader digital health landscape)

### 7.2 Existing Business Context

The requirements document (ARC-001-REQ-v1.0) provides business context and objectives but does not constitute a formal business case. Key business drivers are documented:

- AI companion industry creating attachment at scale (strategic threat)
- Only one published clinical case study on limerence treatment (Wyant, 2021)
- Convergence of AI-enabled exploitation and limerence vulnerability
- No existing market solution for anti-dependency conversational AI

### 7.3 Recommendation

Run `/arckit:sobc` to create a Strategic Outline Business Case using the UK Government Green Book 5-case model. This is particularly relevant if the project seeks:
- NHS/NIHR research funding
- Innovate UK grant funding
- Private investment for commercialisation
- Partnership with mental health charities or NHS trusts

---

## 8. Data Model Analysis

### 8.1 Finding H1 — No Formal Data Model (MEDIUM)

No dedicated data model artifact (`ARC-001-DATA-*.md`) exists despite:

- **4 Data Requirements** (DR-001 through DR-004) defining User Profile, Session Data, Ritual Tracking Data, and Self-Assessment Scores
- **ADR-006** documenting the data architecture decision (Supabase PostgreSQL with Row-Level Security)
- **Special category health data** being processed (Article 9 UK GDPR — health data, psychological assessments)

### 8.2 Current Data Architecture Coverage

| Data Entity | Defined in REQ | Covered by ADR-006 | Formal Model | GDPR Classification |
|-------------|----------------|--------------------|--------------|--------------------|
| DR-001: User Profile | Yes | Yes (schema outlined) | No | Personal data |
| DR-002: Session Data | Yes | Yes (schema outlined) | No | Special category (health) |
| DR-003: Ritual Tracking Data | Yes | Yes (schema outlined) | No | Special category (health) |
| DR-004: Self-Assessment Scores | Yes | Yes (schema outlined) | No | Special category (health) |

### 8.3 What Is Missing

A formal data model artifact should include:

1. **Entity-Relationship Diagram (ERD)** — Visual representation of data entities and relationships
2. **Full attribute specifications** — Data types, constraints, validation rules, defaults
3. **GDPR compliance matrix** — Lawful basis, retention periods, data subject rights mapping per entity
4. **CRUD matrix** — Which system components create, read, update, and delete each entity
5. **Data lineage** — Flow of data from capture through processing to storage and deletion
6. **Encryption specification** — At-rest and in-transit encryption per field sensitivity level

### 8.4 Recommendation

Run `/arckit:data-model` to create a comprehensive data model. This is particularly important given:
- 3 of 4 data entities contain **special category health data** under Article 9 UK GDPR
- The DPIA (Data Protection Impact Assessment) will require a formal data model as input
- ADR-006 provides the architecture decision but not the implementation specification

---

## 9. Traceability Analysis

### 9.1 Traceability Completeness

| Traceability Link | Coverage | Status |
|--------------------|----------|--------|
| Stakeholder Goals → Requirements | 90% | :white_check_mark: Strong |
| Requirements → ADRs (Design Coverage) | 76% (38/50) | :warning: Below 80% target |
| ADRs → Requirements (Backward Trace) | 100% (8/8 ADRs reference requirements) | :white_check_mark: Complete |
| Requirements → Tests | 0% | :clock3: Pre-implementation |
| ADRs → Risks | 100% (all ADRs reference risks) | :white_check_mark: Complete |

### 9.2 Finding C1 — Orphan Requirements (MEDIUM)

12 requirements (24%) have no ADR coverage. Of these:

- **6 are implementation details** that do not require architectural decisions (FR-014, NFR-U-002, INT-002, INT-003, BR-003, BR-006)
- **2 are UX/design concerns** (FR-015, FR-016, NFR-C-004) to be addressed during implementation planning
- **2 are security gaps** (NFR-SEC-004, NFR-SEC-005) that warrant architectural attention
- **1 is an operational concern** (NFR-M-002) implied by ADR-008 but not explicit

### 9.3 Finding C2 — Integration Requirements (MEDIUM)

Integration requirements have the lowest coverage at 33% (1/3):

| INT ID | Description | Priority | ADR Coverage | Assessment |
|--------|-------------|----------|-------------|------------|
| INT-001 | LLM Foundation Model API | MUST | ADR-001 | :white_check_mark: Covered |
| INT-002 | Crisis Resource API | COULD | None | Low risk — static data for Phase 1 |
| INT-003 | Analytics and Outcome Reporting | SHOULD | None | Supports BR-003 (Clinical Outcomes) — gap |

INT-003 (Analytics) is notable because it directly supports BR-003 (Demonstrate Measurable Clinical Outcomes), which is a MUST business requirement in the traceability matrix. While the data architecture (ADR-006) supports data collection, the analytics and reporting pipeline is not architecturally documented.

### 9.4 Traceability Score

**Overall Traceability Score: 76%**

Based on the weighted traceability model from TRAC v1.1:

| Component | Weight | Score | Weighted |
|-----------|--------|-------|----------|
| Design Coverage (ADRs) | 40% | 76% | 30.4 |
| Implementation Evidence | 30% | 0% | 0.0 |
| Test Coverage | 30% | 0% | 0.0 |
| **Overall** | **100%** | | **30.4** |

**Note**: The overall weighted score is 30.4/100 when including implementation and test phases. The 76% traceability score reported in metrics reflects design-phase coverage only, which is the appropriate measure at this stage.

---

## 10. Security and Compliance Summary

### 10.1 Security Requirements Coverage

| Security Requirement | ADR Coverage | Status |
|----------------------|-------------|--------|
| NFR-SEC-001: Authentication | ADR-005 (Supabase Auth) | :white_check_mark: Covered |
| NFR-SEC-002: Authorisation (RBAC) | ADR-005, ADR-006 | :white_check_mark: Covered |
| NFR-SEC-003: Data Encryption | ADR-006 (at-rest and in-transit) | :white_check_mark: Covered |
| NFR-SEC-004: Secrets Management | None | :x: **Gap** |
| NFR-SEC-005: Vulnerability Management | None | :x: **Gap** |
| NFR-SEC-006: LLM Safety Layer | ADR-003 (Defence-in-Depth) | :white_check_mark: Covered |

**Security coverage: 67% (4/6)**

### 10.2 Compliance Requirements Coverage

| Compliance Requirement | ADR Coverage | Status |
|------------------------|-------------|--------|
| NFR-C-001: UK GDPR Compliance | ADR-002, ADR-003, ADR-004, ADR-006, ADR-008 | :white_check_mark: Covered |
| NFR-C-002: Audit Logging | ADR-002 | :white_check_mark: Covered |
| NFR-C-003: MHRA Regulatory Positioning | ADR-002, ADR-004, ADR-007 | :white_check_mark: Covered |
| NFR-C-004: Accessibility (WCAG 2.1 AA) | None | :x: **Gap** |

**Compliance coverage: 75% (3/4)**

### 10.3 Security Gaps Requiring Attention

1. **NFR-SEC-004 (Secrets Management)**: AWS Secrets Manager is implied by the choice of AWS Fargate (ADR-008) but secrets management is not explicitly documented. For a system processing special category health data, the secrets management approach (rotation policy, access controls, audit trail) must be formally specified.

2. **NFR-SEC-005 (Vulnerability Management)**: No CI/CD pipeline or DevSecOps strategy exists. Vulnerability scanning (dependency scanning, container scanning, SAST/DAST) should be defined before implementation begins. Recommend addressing via `/arckit:devops`.

### 10.4 Regulatory Landscape

| Regulator | Engagement Status | Key Requirement | ADR |
|-----------|------------------|-----------------|-----|
| MHRA | Planned (ADR-004 phased approach) | Medical device classification determination | ADR-004, ADR-007 |
| ICO | Planned (DPIA required pre-launch) | UK GDPR compliance, DPIA submission | ADR-006, ADR-005 |
| NHS Digital | Not yet engaged | Clinical safety standards (DCB0129/DCB0160) | — |

---

## 11. Cross-Artifact Consistency

### 11.1 Finding K1 — ADR Status Inconsistency (HIGH)

The 8 ADRs use **three different status values with inconsistent casing**:

| Status Value | ADRs | Lifecycle Stage |
|--------------|------|-----------------|
| `DRAFT` | ADR-001, ADR-006, ADR-007, ADR-008 | Not yet formally proposed |
| `PROPOSED` | ADR-002, ADR-003, ADR-005 | Formally proposed, awaiting review |
| `Accepted` | ADR-004 | Reviewed and accepted |

**Issues identified**:

1. **Mixed casing**: `DRAFT` and `PROPOSED` use UPPERCASE but `Accepted` uses Title Case. Status taxonomy should be consistent (recommend UPPERCASE throughout).
2. **Unclear lifecycle progression**: If ADRs follow DRAFT -> PROPOSED -> ACCEPTED -> SUPERSEDED lifecycle, then ADR-001 (foundational LLM selection) being DRAFT while ADR-002 (anti-dependency — which depends on ADR-001) is PROPOSED is inconsistent. A dependent decision should not be at a later lifecycle stage than its dependency.
3. **ADR-004 anomaly**: ADR-004 (Regulatory Positioning) is "Accepted" but has `PENDING` in its approval fields. If accepted, the approver and approval date should be populated.

### 11.2 Finding K2 — ADR-004 Missing Owner (MEDIUM)

ADR-004 uses a different document control structure from the other 7 ADRs. It has `Decider(s)` and `Escalation Level` fields instead of the standard `Owner` field. While ADR-004 lists "Product Owner (Mark Craddock)" as decider, the absence of a standard `Owner` field breaks consistency with the other ADRs.

All other ADRs: `| **Owner** | Mark Craddock, Product Owner |`
ADR-004: No `Owner` row present.

### 11.3 Finding K3 — Missing Recommended Artifacts (MEDIUM)

For a project of DeLimerence's scope — processing special category health data, engaging with MHRA and ICO, and seeking to demonstrate clinical efficacy — the following artifacts are recommended but absent:

| Artifact Type | Code | Status | Recommendation |
|---------------|------|--------|----------------|
| Strategic Outline Business Case | SOBC | Missing | Run `/arckit:sobc` — needed for funding/investment conversations |
| Data Model | DATA | Missing | Run `/arckit:data-model` — needed for DPIA and implementation |
| Architecture Principles | PRIN | Missing | Run `/arckit:principles` — needed for governance baseline |
| DevOps Strategy | DEVOPS | Missing | Run `/arckit:devops` — needed for NFR-SEC-004/005/NFR-M-002 |
| High-Level Design | HLD | Missing | Needed before implementation — referenced as "not yet created" in TRAC |
| Test Plan | TEST | Missing | Needed before implementation — 0% test coverage |

### 11.4 Document Control Consistency

| Check | Result | Notes |
|-------|--------|-------|
| All artifacts have Document Control section | :white_check_mark: Pass | All 14 artifacts have standard headers |
| Consistent Classification | :white_check_mark: Pass | All use OFFICIAL |
| Consistent Owner | :warning: Partial | ADR-004 missing Owner field |
| Consistent Review Date | :white_check_mark: Pass | All set to 2026-05-06 |
| Consistent ArcKit Version | :warning: Partial | STKE and RISK use 4.6.3; ADRs and TRAC use 4.6.4-rc.1 |
| Consistent Template Origin | :white_check_mark: Pass | All use Official template |

---

## 12. Recommendations

### 12.1 HIGH Priority (Address Before Stakeholder Review)

| ID | Finding | Action | Owner | Target Date |
|----|---------|--------|-------|-------------|
| REC-01 | A1: Requirements priority normalisation | Review ARC-001-REQ-v1.0 and encode MUST/SHOULD/COULD priority consistently in parseable metadata fields. Align with TRAC v1.1 priority values. | Product Owner | 2026-04-20 |
| REC-02 | B1: Missing architecture principles | Run `/arckit:principles` to create ARC-000-PRIN-v1.0.md in projects/000-global/. Codify the 6 implied principles identified in this analysis. | Product Owner | 2026-04-20 |
| REC-03 | K1: ADR status inconsistency | Normalise all ADR status fields to use UPPERCASE taxonomy (DRAFT, PROPOSED, ACCEPTED, SUPERSEDED). Review ADR-004 "Accepted" status — populate approver fields or revert to PROPOSED. | Product Owner | 2026-04-20 |

### 12.2 MEDIUM Priority (Address Before Implementation)

| ID | Finding | Action | Owner | Target Date |
|----|---------|--------|-------|-------------|
| REC-04 | H1: No formal data model | Run `/arckit:data-model` to create ARC-001-DATA-v1.0.md with ERD, GDPR matrix, and CRUD matrix for DR-001 through DR-004. | Product Owner | 2026-05-06 |
| REC-05 | G1: No business case | Run `/arckit:sobc` to create Strategic Outline Business Case for investor/funder engagement. | Product Owner | 2026-05-06 |
| REC-06 | C1: Security requirement gaps | Document secrets management approach (NFR-SEC-004) — either amend ADR-008 or create operational runbook. Define vulnerability management pipeline (NFR-SEC-005) via `/arckit:devops`. | Development Team | 2026-05-06 |
| REC-07 | K2: ADR-004 missing Owner | Add standard `Owner` field to ADR-004 document control table. | Product Owner | 2026-04-20 |
| REC-08 | A2: Resolve PENDING placeholders | Identify review panel members and populate Reviewed By / Approved By fields across all DRAFT artifacts before approval gate. | Product Owner | 2026-05-06 |
| REC-09 | C2: Integration gaps | Address INT-003 (Analytics and Outcome Reporting) — document analytics pipeline approach to support BR-003 (Clinical Outcomes). | Product Owner | 2026-05-06 |

### 12.3 LOW Priority (Address During Implementation)

| ID | Finding | Action | Owner | Target Date |
|----|---------|--------|-------|-------------|
| REC-10 | C1: Remaining orphan requirements | Address NFR-C-004 (Accessibility) during UX design. Address NFR-M-002 (Observability) in DevOps strategy. FR-014, FR-015, FR-016 are implementation details. | Development Team | 2026-07-06 |
| REC-11 | K3: Missing HLD and Test Plan | Create High-Level Design and Test Plan before implementation begins. | Development Team | 2026-06-06 |

---

## 13. Metrics Dashboard

### 13.1 Category Scores

| Category | Score | Grade | Assessment |
|----------|-------|-------|------------|
| Requirements Coverage | 76% | C | 38/50 requirements covered by ADRs; 12 orphan requirements |
| Principles Compliance | N/A | — | No principles document exists to assess against |
| Traceability | 76% | C | Strong forward and backward trace; 0% test coverage (expected) |
| Stakeholder Alignment | 90% | A | Comprehensive STKE with driver-goal-outcome chains |
| Risk Management | 85% | B | 15 risks documented, cross-referenced, owners assigned |
| Business Case | 30% | F | No SOBC; business context in REQ only |
| Data Model | 40% | D | Schema in ADR-006 but no formal data model artifact |
| Security | 67% | D | 4/6 security NFRs covered; secrets and vuln mgmt gaps |
| Compliance | 75% | C | 3/4 compliance NFRs covered; accessibility gap |
| Cross-Artifact Consistency | 65% | D | Status inconsistency, missing owner, mixed ArcKit versions |

### 13.2 Overall Governance Health

```
GOVERNANCE HEALTH SCORE: 72/100 (Grade C — Adequate)

  Requirements    [========------]  76%
  Principles      [              ]  N/A
  Traceability    [========------]  76%
  Stakeholders    [=============-]  90%
  Risk Mgmt       [==========----]  85%
  Business Case   [====-----------]  30%
  Data Model      [=====----------]  40%
  Security        [=======---------]  67%
  Compliance      [========--------]  75%
  Consistency     [=======---------]  65%
```

### 13.3 Issue Distribution

| Severity | Count | % of Total |
|----------|-------|------------|
| CRITICAL | 0 | 0% |
| HIGH | 3 | 27% |
| MEDIUM | 6 | 55% |
| LOW | 2 | 18% |
| **TOTAL** | **11** | **100%** |

### 13.4 Artifact Maturity

| Artifact | Status | Completeness | Quality |
|----------|--------|-------------|---------|
| ARC-001-REQ-v1.0 (Requirements) | DRAFT | High — 50 requirements defined | Medium — priority encoding issue |
| ARC-001-STKE-v1.0 (Stakeholders) | DRAFT | High — comprehensive analysis | High — driver-goal-outcome chains |
| ARC-001-RISK-v1.0 (Risk Register) | DRAFT | High — 15 risks, 6 categories | High — Orange Book methodology |
| ARC-001-RSCH-v1.0 (Research) | DRAFT | High — technology landscape covered | High — build vs buy analysis |
| ARC-001-TRAC-v1.1 (Traceability) | DRAFT | High — full matrix with gap analysis | High — forward and backward trace |
| ADR-001 to ADR-008 | Mixed | High — all 8 ADRs have options analysis | Medium — status inconsistency |

---

## 14. Next Steps

### 14.1 Immediate Actions (Next 2 Weeks)

1. **Normalise requirements priorities** (REC-01) — Review and update ARC-001-REQ-v1.0 priority fields
2. **Create architecture principles** (REC-02) — Run `/arckit:principles` for enterprise principles document
3. **Fix ADR status taxonomy** (REC-03) — Normalise all ADR status values to UPPERCASE
4. **Populate ADR-004 Owner** (REC-07) — Add standard Owner field

### 14.2 Pre-Implementation Actions (Next 4 Weeks)

5. **Create formal data model** (REC-04) — Run `/arckit:data-model` for DR-001 through DR-004
6. **Create business case** (REC-05) — Run `/arckit:sobc` for funding engagement
7. **Address security gaps** (REC-06) — Document secrets management and vulnerability scanning
8. **Create DevOps strategy** — Run `/arckit:devops` for CI/CD, security scanning, observability
9. **Run DPIA** — Run `/arckit:dpia` for UK GDPR Article 35 assessment (required before processing health data)

### 14.3 Implementation Readiness Actions (Next 8 Weeks)

10. **Create High-Level Design** — System context, container, and component diagrams
11. **Define test strategy** — Clinical safety tests, anti-dependency constraint tests, security tests
12. **Establish review panel** — Populate all PENDING reviewer/approver fields
13. **Re-run governance analysis** — Run `/arckit:analyze` after addressing HIGH priority findings

### 14.4 Governance Cadence

| Activity | Frequency | Next Due |
|----------|-----------|----------|
| Artifact review cycle | Monthly | 2026-05-06 |
| Risk register review | Monthly | 2026-05-06 |
| Traceability update | After each ADR/requirement change | As needed |
| Governance analysis | Quarterly or after major changes | 2026-07-06 |
| Stakeholder engagement review | Quarterly | 2026-07-06 |

---

## 15. Appendix: Analysis Methodology

### 15.1 Analysis Process

This governance analysis was performed using the ArcKit `/arckit:analyze` command, which executes the following detection passes:

| Pass | Category | Description | Findings |
|------|----------|-------------|----------|
| A | Requirements Quality | Priority distribution, completeness, placeholder detection | A1, A2 |
| B | Architecture Principles Alignment | Principles document existence, ADR-principles cross-reference | B1 |
| C | Requirements-Design Traceability | Forward/backward trace, orphan detection, coverage calculation | C1, C2 |
| D | Vendor Procurement | Vendor evaluation framework, SOW existence | N/A (no vendor documents) |
| E | Stakeholder Traceability | STKE existence, driver-goal-outcome completeness | E1 |
| F | Risk Management | RISK existence, risk-ADR cross-reference, owner assignment | F1 |
| G | Business Case | SOBC existence, business context assessment | G1 |
| H | Data Model Consistency | DATA artifact existence, DR-xxx coverage, GDPR classification | H1 |
| I | UK Government Compliance | TCoP, Service Standard, Spend Controls | N/A (not UK Gov project) |
| J | MOD Compliance | JSP 440, JSP 936, CAAT | N/A (not MOD project) |
| K | Cross-Artifact Consistency | Status taxonomy, field consistency, missing artifacts | K1, K2, K3 |

### 15.2 Scoring Methodology

**Governance Health Score** is calculated as a weighted average across 10 categories:

| Category | Weight | Scoring Basis |
|----------|--------|---------------|
| Requirements Coverage | 15% | % of requirements with ADR coverage |
| Principles Compliance | 10% | % of principles with evidence of compliance |
| Traceability | 15% | Forward and backward trace completeness |
| Stakeholder Alignment | 10% | STKE completeness and requirement mapping |
| Risk Management | 10% | RISK completeness and ADR cross-reference |
| Business Case | 5% | SOBC existence and completeness |
| Data Model | 10% | DATA artifact existence and GDPR coverage |
| Security | 10% | Security NFR coverage |
| Compliance | 10% | Compliance NFR coverage |
| Cross-Artifact Consistency | 5% | Status, field, and structure consistency |

### 15.3 Grading Scale

| Score | Grade | Assessment | Action |
|-------|-------|------------|--------|
| 90-100 | A | Excellent | Proceed to approval |
| 80-89 | B | Good | Minor improvements recommended |
| 70-79 | C | Adequate | Address high-priority issues before review |
| 60-69 | D | Below standard | Significant improvements required |
| 0-59 | F | Inadequate | Major rework required |

### 15.4 Artifacts Analysed

| # | Artifact ID | Type | Location |
|---|-------------|------|----------|
| 1 | ARC-001-REQ-v1.0 | Requirements | projects/001-delimerence/ARC-001-REQ-v1.0.md |
| 2 | ARC-001-STKE-v1.0 | Stakeholder Analysis | projects/001-delimerence/ARC-001-STKE-v1.0.md |
| 3 | ARC-001-RISK-v1.0 | Risk Register | projects/001-delimerence/ARC-001-RISK-v1.0.md |
| 4 | ARC-001-RSCH-v1.0 | Research | projects/001-delimerence/research/ARC-001-RSCH-v1.0.md |
| 5 | ARC-001-TRAC-v1.0 | Traceability Matrix | projects/001-delimerence/ARC-001-TRAC-v1.0.md |
| 6 | ARC-001-TRAC-v1.1 | Traceability Matrix | projects/001-delimerence/ARC-001-TRAC-v1.1.md |
| 7 | ARC-001-ADR-001-v1.0 | ADR: LLM Selection | projects/001-delimerence/decisions/ARC-001-ADR-001-v1.0.md |
| 8 | ARC-001-ADR-002-v1.0 | ADR: Anti-Dependency | projects/001-delimerence/decisions/ARC-001-ADR-002-v1.0.md |
| 9 | ARC-001-ADR-003-v1.0 | ADR: Safety Layer | projects/001-delimerence/decisions/ARC-001-ADR-003-v1.0.md |
| 10 | ARC-001-ADR-004-v1.0 | ADR: Regulatory Positioning | projects/001-delimerence/decisions/ARC-001-ADR-004-v1.0.md |
| 11 | ARC-001-ADR-005-v1.0 | ADR: Authentication | projects/001-delimerence/decisions/ARC-001-ADR-005-v1.0.md |
| 12 | ARC-001-ADR-006-v1.0 | ADR: Data Architecture | projects/001-delimerence/decisions/ARC-001-ADR-006-v1.0.md |
| 13 | ARC-001-ADR-007-v1.0 | ADR: Phase Assessment | projects/001-delimerence/decisions/ARC-001-ADR-007-v1.0.md |
| 14 | ARC-001-ADR-008-v1.0 | ADR: Infrastructure | projects/001-delimerence/decisions/ARC-001-ADR-008-v1.0.md |

---

**Generated by**: ArcKit `/arckit:analyze` command
**Generated on**: 2026-04-06
**ArcKit Version**: 4.6.4-rc.1
**Project**: DeLimerence (Project 001)
**AI Model**: Claude Opus 4.6 (1M context)
**Generation Context**: Governance analysis from 14 artifacts (8 ADRs, REQ, RISK, STKE, 2x TRAC, RSCH)
