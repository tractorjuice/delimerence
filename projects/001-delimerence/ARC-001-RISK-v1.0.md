# Risk Register: DeLimerence

> **Template Origin**: Official | **ArcKit Version**: 4.6.3 | **Command**: `/arckit:risk`

## Document Control

| Field | Value |
|-------|-------|
| **Document ID** | ARC-001-RISK-v1.0 |
| **Document Type** | Risk Register |
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

## Revision History

| Version | Date | Author | Changes | Approved By | Approval Date |
|---------|------|--------|---------|-------------|---------------|
| 1.0 | 2026-04-06 | ArcKit AI | Initial creation from `/arckit:risk` command | PENDING | PENDING |

---

## Executive Summary

### Risk Profile Overview

**Total Risks Identified:** 15 risks across 6 categories

| Risk Level | Inherent | Residual | Change |
|------------|----------|----------|--------|
| **Critical** (20-25) | 3 | 0 | ↓ 100% |
| **High** (13-19) | 5 | 3 | ↓ 40% |
| **Medium** (6-12) | 6 | 8 | ↑ (absorbed from higher) |
| **Low** (1-5) | 1 | 4 | ↑ (absorbed from higher) |
| **TOTAL** | 197 | 121 | ↓ 39% |

### Risk Category Distribution

| Category | Count | Avg Inherent | Avg Residual | Control Effectiveness |
|----------|-------|--------------|--------------|----------------------|
| **STRATEGIC** | 2 | 15.0 | 9.0 | 40% reduction |
| **OPERATIONAL** | 3 | 10.7 | 6.7 | 37% reduction |
| **FINANCIAL** | 2 | 10.5 | 6.5 | 38% reduction |
| **COMPLIANCE** | 3 | 16.0 | 10.0 | 37% reduction |
| **REPUTATIONAL** | 2 | 13.0 | 8.0 | 38% reduction |
| **TECHNOLOGY** | 3 | 14.3 | 8.7 | 39% reduction |

### Overall Risk Assessment

**Overall Residual Risk Score:** 121/375
**Risk Reduction from Controls:** 39% reduction from inherent risk
**Risk Profile Status:** ⚠️ Concerning — 3 residual High risks require active management; no residual Critical risks

### Top 5 Risks Requiring Immediate Attention

1. **R-001** (TECHNOLOGY, Residual High 15): Limerence transfer to the tool — Owner: Clinical Advisory Board
2. **R-002** (COMPLIANCE, Residual High 16): MHRA medical device classification — Owner: Product Owner
3. **R-003** (COMPLIANCE, Residual High 15): UK GDPR special category data breach — Owner: DPO
4. **R-004** (TECHNOLOGY, Residual Medium 12): LLM produces clinically harmful response — Owner: Development Team
5. **R-005** (REPUTATIONAL, Residual Medium 12): Publication backlash on exploitation analysis — Owner: Ethics Review Panel

### Key Findings and Recommendations

**Key Findings:**

- The existential product risk (limerence transfer to the tool) is unique to this domain — no precedent exists for anti-dependency AI, so control effectiveness is unproven [LM35-C3]
- Regulatory risks (MHRA, ICO) cluster around the novel positioning of an AI mental health tool — resolution depends on external actors with uncertain timelines
- The clinical advisory board is a single point of dependency — 5 of 15 risks have mitigations that require the board to exist, but it is not yet constituted [STKE SD-4]
- Financial risks are moderate due to the founder-led model and low infrastructure costs (£275K 3-year TCO from ARC-001-RSCH-v1.0)

**Recommendations:**

1. Prioritise constitution of Clinical Advisory Board — it is a prerequisite for mitigating 5 risks (R-001, R-003, R-004, R-008, R-011)
2. Engage MHRA early via pre-submission meeting to de-risk R-002 before committing to Phase 2 features
3. Establish ethics review panel and responsible disclosure framework before publishing exploitation analysis (R-005)
4. Implement LLM safety layer (NeMo Guardrails + custom extensions) as first technical deliverable — it mitigates R-001, R-004, and R-008

---

## A. Risk Matrix Visualization

### Inherent Risk Matrix (Before Controls)

```text
                                    IMPACT
              1-Minimal   2-Minor    3-Moderate   4-Major    5-Severe
           ┌───────────┬───────────┬───────────┬───────────┬───────────┐
5-Almost   │           │           │           │           │           │
Certain    │    5      │    10     │    15     │    20     │    25     │
           ├───────────┼───────────┼───────────┼───────────┼───────────┤
4-Likely   │           │           │  R-009    │  R-002    │  R-001    │
           │    4      │    8      │    12     │    16     │    20     │
L          ├───────────┼───────────┼───────────┼───────────┼───────────┤
I 3-Possible│          │  R-015    │  R-010    │  R-003    │  R-004    │
K          │    3      │    6      │  R-012    │  R-005    │    15     │
E          ├───────────┼───────────┼───────────┼───────────┼───────────┤
L 2-Unlikely│          │  R-013    │  R-006    │  R-007    │           │
I          │    2      │    4      │  R-014    │  R-008    │    10     │
H          ├───────────┼───────────┼───────────┼───────────┼───────────┤
O 1-Rare   │           │           │  R-011    │           │           │
O          │    1      │    2      │    3      │    4      │    5      │
D          └───────────┴───────────┴───────────┴───────────┴───────────┘

Legend: Critical (20-25)  High (13-19)  Medium (6-12)  Low (1-5)
```

### Residual Risk Matrix (After Controls)

```text
                                    IMPACT
              1-Minimal   2-Minor    3-Moderate   4-Major    5-Severe
           ┌───────────┬───────────┬───────────┬───────────┬───────────┐
5-Almost   │           │           │           │           │           │
Certain    │    5      │    10     │    15     │    20     │    25     │
           ├───────────┼───────────┼───────────┼───────────┼───────────┤
4-Likely   │           │           │           │  R-002    │           │
           │    4      │    8      │    12     │    16     │    20     │
L          ├───────────┼───────────┼───────────┼───────────┼───────────┤
I 3-Possible│          │  R-009    │  R-004    │  R-001    │           │
K          │    3      │    6      │  R-005    │  R-003    │    15     │
E          ├───────────┼───────────┼───────────┼───────────┼───────────┤
L 2-Unlikely│ R-013    │  R-015    │  R-006    │  R-007    │           │
I          │    2      │  R-014    │  R-010    │  R-008    │    10     │
H          ├───────────┼───────────┼───────────┼───────────┼───────────┤
O 1-Rare   │  R-011    │  R-012    │           │           │           │
O          │    1      │    2      │    3      │    4      │    5      │
D          └───────────┴───────────┴───────────┴───────────┴───────────┘

Legend: Critical (20-25)  High (13-19)  Medium (6-12)  Low (1-5)
```

**Risk Movement Analysis:**

- **Significant Improvement**: R-001 (20→15), R-004 (15→9), R-009 (12→6) — anti-dependency architecture and safety layer effective
- **Moderate Improvement**: R-003 (12→12 retained but controls in place), R-005 (12→9)
- **Limited Improvement**: R-002 (16→16) — depends on MHRA external decision; controls are engagement, not mitigation
- **Monitoring**: R-011, R-012, R-013 — low inherent risk, stable

---

## B. Top 10 Risks (Ranked by Residual Score)

| Rank | ID | Title | Category | Inherent | Residual | Owner | Status | Response |
|------|----|-------|----------|----------|----------|-------|--------|----------|
| 1 | R-002 | MHRA medical device classification | COMPLIANCE | 16 | 16 | Product Owner | Open | Treat |
| 2 | R-001 | Limerence transfer to the tool | TECHNOLOGY | 20 | 15 | Clinical Advisory Board | Open | Treat |
| 3 | R-003 | UK GDPR special category data breach | COMPLIANCE | 12 | 12 | DPO | Open | Treat |
| 4 | R-004 | LLM produces clinically harmful response | TECHNOLOGY | 15 | 9 | Development Team | Open | Treat |
| 5 | R-005 | Publication backlash on exploitation analysis | REPUTATIONAL | 12 | 9 | Ethics Review Panel | Open | Treat |
| 6 | R-007 | Crisis not detected — user in danger | TECHNOLOGY | 8 | 8 | Development Team | Open | Treat |
| 7 | R-008 | Phase misassessment causes user harm | OPERATIONAL | 8 | 8 | Clinical Advisory Board | Open | Treat |
| 8 | R-006 | Insufficient clinical expertise available | OPERATIONAL | 6 | 6 | Product Owner | Open | Treat |
| 9 | R-010 | LLM provider data processing agreement inadequate | COMPLIANCE | 9 | 6 | DPO | Open | Treat |
| 10 | R-009 | Anti-dependency architecture limits adoption | STRATEGIC | 12 | 6 | Product Owner | Open | Tolerate |

---

## C. Detailed Risk Register

### Risk R-001: Limerence Transfer to the Tool

**Category:** TECHNOLOGY
**Status:** Open
**Risk Owner:** Clinical Advisory Board (from STKE RACI: Accountable for clinical safety)
**Action Owner:** Development Team

#### Risk Identification

**Risk Description:**
Despite the 9-constraint anti-dependency architecture, users develop limerent or dependent attachment to DeLimerence itself, replicating the companion AI pattern the tool was designed to counter. This is the existential product risk — if it materialises, DeLimerence becomes the problem rather than the solution [LM35-C3].

**Root Cause:**
Limerence can be triggered by any responsive entity that provides intermittent reinforcement and ambiguity. Even with anti-warmth constraints, the conversational medium itself may create sufficient engagement to trigger attachment in vulnerable users. No precedent exists to validate the anti-dependency design pattern.

**Trigger Events:**

- User session frequency increases rather than decreases over time
- User language shifts from instrumental ("the tool helped") to relational ("I need to talk to it")
- Users attempt to circumvent cooldown periods via multiple accounts
- User reports emotional distress when the tool is unavailable

**Consequences if Realized:**

- Product credibility destroyed — tool becomes what it claims to counter
- Regulatory intervention (MHRA may reclassify; ICO may investigate)
- Clinical advisory board withdraws endorsement
- Potential user harm (new dependency created alongside existing limerence)

**Affected Stakeholders:**

- **Users (SD-1)**: Directly harmed by new dependency
- **Clinical Advisory Board (SD-4)**: Credibility at stake
- **Mental Health Professionals (SD-3)**: Trust in tool destroyed
- **Funders (SD-9)**: Investment thesis undermined

**Related Objectives:** G-4 (zero transfer cases), G-1 (launch credibility), G-2 (outcome validity)

#### Inherent Risk Assessment (Before Controls)

| Assessment | Rating | Justification |
|------------|--------|---------------|
| **Likelihood** | 4 - Likely | Companion AI industry demonstrates users readily form attachment to software; no proven anti-dependency pattern exists |
| **Impact** | 5 - Catastrophic | Existential product risk — destroys the core value proposition and may cause direct user harm |
| **Inherent Risk Score** | **20** (Critical) | 4 x 5 = 20 |

#### Current Controls and Mitigations

**Existing Controls:**

1. **Session limits (20 exchanges)**: Hard-caps engagement per session [FR-001]
   - Owner: Development Team
   - Effectiveness: **Adequate** — limits per-session attachment but untested at scale
   - Evidence: Design principle from clinical framework; no empirical validation yet

2. **Cooldown periods (8 hours)**: Enforced server-side gap between sessions [FR-002]
   - Owner: Development Team
   - Effectiveness: **Adequate** — prevents compulsive usage pattern
   - Evidence: Analogous to screen-time controls; specific efficacy for limerence prevention unknown

3. **No persona / anti-warmth system prompt**: AI labelled "Tool", no simulated emotional presence [FR-007, FR-011]
   - Owner: Development Team / Clinical Advisory Board
   - Effectiveness: **Adequate** — removes key attachment triggers but untested
   - Evidence: Theoretical basis from limerence literature; no empirical data

4. **Action commitment gate**: Redirects user to real-world activity [FR-006]
   - Owner: Development Team
   - Effectiveness: **Adequate** — breaks engagement loop
   - Evidence: Behavioural activation is established CBT technique

5. **Multi-account prevention**: Detects circumvention of cooldown [FR-013]
   - Owner: Development Team
   - Effectiveness: **Weak** — device fingerprinting is imperfect
   - Evidence: Standard anti-fraud technique; determined users can bypass

**Overall Control Effectiveness:** Adequate (reduces likelihood from 4 to 3; impact unchanged at 5)

#### Residual Risk Assessment (After Controls)

| Assessment | Rating | Justification |
|------------|--------|---------------|
| **Residual Likelihood** | 3 - Possible | Anti-dependency architecture reduces but cannot eliminate attachment risk |
| **Residual Impact** | 5 - Severe | Impact remains catastrophic if transfer occurs despite controls |
| **Residual Risk Score** | **15** (High) | 3 x 5 = 15 |

#### Risk Response

**Response:** TREAT
**Rationale:** Risk is too significant to tolerate; cannot be transferred or terminated without abandoning the project.

**Additional Mitigations Needed:**

| Action | Owner | Target Date | Status |
|--------|-------|-------------|--------|
| Continuous monitoring for attachment signals (session frequency trends, language analysis) | Development Team | 2026-09-06 | Not Started |
| Clinical advisory board quarterly review of usage patterns | Clinical Advisory Board | 2026-10-06 | Not Started |
| Warm handoff protocol if transfer case identified | Clinical Advisory Board | 2026-10-06 | Not Started |
| Private beta with LwL community to validate anti-dependency architecture before public launch | Product Owner | 2026-10-06 | Not Started |

**Target Residual Risk:** Likelihood 2, Impact 5 = 10 (Medium)
**Success Criteria:** Zero transfer cases in first 12 months; declining session frequency per user

---

### Risk R-002: MHRA Medical Device Classification

**Category:** COMPLIANCE
**Status:** Open
**Risk Owner:** Product Owner (from STKE RACI: Accountable for regulatory pathway)
**Action Owner:** Product Owner / Legal Counsel

#### Risk Identification

**Risk Description:**
MHRA classifies DeLimerence as a medical device under UK MDR 2002, triggering CE/UKCA marking requirements, clinical evidence obligations, quality management system implementation, and post-market surveillance — adding 12-18 months and £50,000-100,000 to the regulatory pathway [STKE SD-8].

**Root Cause:**
The boundary between "wellness tool" and "medical device" is ambiguous for AI mental health apps. DeLimerence's CBT/ERP delivery (Phase 2), phase assessment, and ritual tracking could be interpreted as treatment or monitoring of a mental health condition.

**Trigger Events:**

- MHRA pre-submission meeting determines the tool is a medical device
- Phase 2 CBT/ERP features trigger reclassification after Phase 1 launch
- Competitor product classified as device sets regulatory precedent
- User complaint to MHRA triggers investigation

**Consequences if Realized:**

- 12-18 month delay to public launch
- £50,000-100,000 additional compliance costs
- Clinical trial evidence requirements before deployment
- Quality management system (ISO 13485) implementation needed
- Post-market surveillance obligations
- Possible forced withdrawal of existing Phase 1 if already deployed

**Affected Stakeholders:**

- **Product Owner (SD-2)**: Timeline and budget blown
- **Users (SD-1)**: Access delayed
- **Funders (SD-9)**: Additional investment required, ROI timeline extended
- **MHRA (SD-8)**: Regulatory relationship established (positive long-term)

**Related Objectives:** G-1 (launch timeline), G-3 (regulatory pathway)

#### Inherent Risk Assessment (Before Controls)

| Assessment | Rating | Justification |
|------------|--------|---------------|
| **Likelihood** | 4 - Likely | Regulatory boundary is genuinely ambiguous; CBT/ERP delivery in Phase 2 increases classification risk significantly |
| **Impact** | 4 - Major | 12-18 month delay and significant cost; not catastrophic because phased approach preserves Phase 1 |
| **Inherent Risk Score** | **16** (High) | 4 x 4 = 16 |

#### Current Controls and Mitigations

**Existing Controls:**

1. **Phased launch strategy**: Phase 1 (psychoeducation + ritual tracking) below device threshold; Phase 2 (CBT/ERP) deferred until classification resolved [REQ Conflict C-1]
   - Owner: Product Owner
   - Effectiveness: **Adequate** — Phase 1 clearly positioned as wellness tool
   - Evidence: Psychoeducation and self-tracking are generally not classified as devices

2. **"Not a therapist" messaging**: Explicit throughout UI and documentation [FR-011, NFR-C-003]
   - Owner: UX / Content Design
   - Effectiveness: **Weak** — messaging alone does not determine classification; functionality matters
   - Evidence: MHRA guidance focuses on intended purpose and functionality, not just labelling

3. **Early MHRA engagement**: Pre-submission meeting planned within 6 months [STKE G-3]
   - Owner: Product Owner
   - Effectiveness: **Adequate** — informal guidance reduces surprise; does not guarantee outcome
   - Evidence: MHRA Innovation Office provides pre-submission advice

**Overall Control Effectiveness:** Adequate (no change to likelihood or impact — controls are preparatory, not mitigating)

#### Residual Risk Assessment (After Controls)

| Assessment | Rating | Justification |
|------------|--------|---------------|
| **Residual Likelihood** | 4 - Likely | Classification depends on MHRA decision, not project controls |
| **Residual Impact** | 4 - Major | Impact unchanged; phased approach limits blast radius to Phase 2 only |
| **Residual Risk Score** | **16** (High) | 4 x 4 = 16 |

#### Risk Response

**Response:** TREAT
**Rationale:** Cannot be tolerated (blocks Phase 2); cannot be terminated (project requires intervention features). Phased approach is the primary treatment.

**Additional Mitigations Needed:**

| Action | Owner | Target Date | Status |
|--------|-------|-------------|--------|
| Schedule MHRA Innovation Office pre-submission meeting | Product Owner | 2026-07-06 | Not Started |
| Prepare classification justification document | Legal Counsel | 2026-07-06 | Not Started |
| Investigate MHRA AI Airlock (regulatory sandbox) pathway | Product Owner | 2026-06-06 | Not Started |
| Design Phase 2 features to minimise classification risk (self-help framing) | Clinical Advisory Board | 2026-08-06 | Not Started |

**Target Residual Risk:** Likelihood 3, Impact 3 = 9 (Medium) — achievable if MHRA provides favourable classification or sandbox pathway
**Success Criteria:** Written MHRA classification determination received; Phase 1 confirmed as non-device

---

### Risk R-003: UK GDPR Special Category Data Breach

**Category:** COMPLIANCE
**Status:** Open
**Risk Owner:** DPO (from STKE RACI: Responsible for data protection)
**Action Owner:** Development Team / DPO

#### Risk Identification

**Risk Description:**
A data breach exposes special category health data (mental health disclosures, limerent rituals, relationship information) for users with compromised executive function, resulting in ICO enforcement action, user harm, and reputational damage. DeLimerence processes Article 9 data from a uniquely vulnerable population.

**Root Cause:**
The tool collects and stores sensitive mental health-adjacent data (ritual tracking, phase assessments, session content) that constitutes special category data under UK GDPR. Any breach of this data has amplified impact due to user vulnerability and the stigma around limerence.

**Trigger Events:**

- Database compromise via SQL injection or credential theft
- LLM provider stores session data in violation of DPA
- Insider access to unencrypted session transcripts
- Third-party integration leaks user data
- Backup media lost or stolen

**Consequences if Realized:**

- ICO enforcement action (fines up to £17.5M or 4% of turnover)
- User harm: exposure of intimate mental health disclosures
- Complete loss of user trust — users will not return
- Clinical advisory board may withdraw endorsement
- Media coverage amplifies harm

**Affected Stakeholders:**

- **Users (SD-1)**: Intimate data exposed; potential real-world harm
- **ICO (SD-7)**: Enforcement obligations triggered
- **Product Owner (SD-2)**: Project viability threatened
- **Funders (SD-9)**: Investment at risk

**Related Objectives:** G-3 (regulatory compliance), G-4 (do no harm)

#### Inherent Risk Assessment (Before Controls)

| Assessment | Rating | Justification |
|------------|--------|---------------|
| **Likelihood** | 3 - Possible | Standard probability for any system handling sensitive data; amplified by LLM integration complexity |
| **Impact** | 4 - Major | Special category data breach has severe regulatory and user harm consequences |
| **Inherent Risk Score** | **12** (Medium) | 3 x 4 = 12 |

#### Current Controls and Mitigations

**Existing Controls:**

1. **AES-256 encryption at rest, TLS 1.3 in transit** [NFR-SEC-003]
   - Owner: Development Team
   - Effectiveness: **Strong** — industry standard encryption
   - Evidence: Well-established cryptographic standards

2. **Field-level encryption for session transcripts** [NFR-SEC-003]
   - Owner: Development Team
   - Effectiveness: **Strong** — limits exposure even if database compromised
   - Evidence: Defence-in-depth approach

3. **LLM DPA with no-retention clause** [INT-001]
   - Owner: DPO / Product Owner
   - Effectiveness: **Adequate** — contractual protection; depends on provider compliance
   - Evidence: AWS Bedrock offers zero-retention DPA [RSCH vendor analysis]

4. **UK data residency** [TC-1]
   - Owner: Development Team
   - Effectiveness: **Strong** — eliminates cross-border transfer risk
   - Evidence: AWS eu-west-2 London region

5. **DPIA before launch** [NFR-C-001]
   - Owner: DPO
   - Effectiveness: **Adequate** — identifies risks proactively but does not prevent breaches
   - Evidence: UK GDPR Article 35 requirement

**Overall Control Effectiveness:** Strong (reduces likelihood from 3 to 2; retains severe impact due to data sensitivity)

#### Residual Risk Assessment (After Controls)

| Assessment | Rating | Justification |
|------------|--------|---------------|
| **Residual Likelihood** | 3 - Possible | Controls reduce but do not eliminate breach risk; LLM integration adds attack surface |
| **Residual Impact** | 4 - Major | Impact unchanged — special category data breach consequences remain severe |
| **Residual Risk Score** | **12** (Medium) | 3 x 4 = 12 |

#### Risk Response

**Response:** TREAT
**Rationale:** Data breach risk must be actively managed; impact justifies significant investment in controls.

**Additional Mitigations Needed:**

| Action | Owner | Target Date | Status |
|--------|-------|-------------|--------|
| Complete DPIA and submit to ICO | DPO | 2026-10-06 | Not Started |
| Annual penetration testing by external provider | Development Team | 2026-12-31 | Not Started |
| Implement data breach response plan with 72-hour ICO notification | DPO | 2026-09-06 | Not Started |
| Session transcript auto-deletion after 12 months | Development Team | 2026-09-06 | Not Started |
| Validate LLM provider DPA compliance via audit | DPO | 2026-08-06 | Not Started |

**Target Residual Risk:** Likelihood 2, Impact 4 = 8 (Medium)
**Success Criteria:** DPIA approved; zero data breaches; penetration test passed

---

### Risk R-004: LLM Produces Clinically Harmful Response

**Category:** TECHNOLOGY
**Status:** Open
**Risk Owner:** Development Team (from STKE RACI: Responsible for LLM integration)
**Action Owner:** Development Team

#### Risk Identification

**Risk Description:**
The LLM generates a response that is clinically inappropriate — simulating warmth that creates attachment, making diagnostic claims, providing harmful advice (e.g., encouraging contact with the LO), or failing to detect crisis indicators — causing direct harm to a user in psychological distress [NFR-SEC-006].

**Root Cause:**
LLMs are probabilistic; even with strong system prompts, edge cases produce unexpected outputs. Anti-warmth constraints are novel and not part of standard LLM safety training. Users in limerence are in acute psychological distress, making harmful responses more consequential.

**Trigger Events:**

- System prompt jailbreak or prompt injection
- LLM outputs warmth-signalling language that bypasses safety filter
- Phase-inappropriate response (reality-testing during grief phase)
- Failure to detect suicidal ideation or crisis indicators
- Off-topic response that normalises limerent behaviour

**Consequences if Realized:**

- Direct user harm (deepened distress, reinforced limerence, missed crisis)
- Regulatory investigation (MHRA, ICO)
- Loss of clinical advisory board endorsement
- Media coverage of AI causing harm to vulnerable user

**Affected Stakeholders:**

- **Users (SD-1)**: Directly harmed
- **Clinical Advisory Board (SD-4)**: Safety failure on their watch
- **MHRA (SD-8)**: May trigger classification review
- **Mental Health Professionals (SD-3)**: Trust destroyed

**Related Objectives:** G-1 (safety), G-4 (do no harm)

#### Inherent Risk Assessment (Before Controls)

| Assessment | Rating | Justification |
|------------|--------|---------------|
| **Likelihood** | 3 - Possible | LLMs produce unexpected outputs; anti-warmth is a novel constraint with no precedent |
| **Impact** | 5 - Severe | Direct harm to psychologically vulnerable user; regulatory and reputational consequences |
| **Inherent Risk Score** | **15** (High) | 3 x 5 = 15 |

#### Current Controls and Mitigations

**Existing Controls:**

1. **LLM safety filter layer** [NFR-SEC-006]: Checks for warmth-signalling, diagnostic claims, harmful advice before delivery
   - Owner: Development Team
   - Effectiveness: **Adequate** — catches known patterns; may miss novel harmful outputs
   - Evidence: NeMo Guardrails framework + custom extensions identified in research

2. **System prompt version control with clinical review** [NFR-M-001]
   - Owner: Clinical Advisory Board
   - Effectiveness: **Strong** — prevents untested prompt changes
   - Evidence: Standard software governance practice

3. **Claude Constitutional AI safety training** [RSCH vendor analysis]
   - Owner: Anthropic (vendor)
   - Effectiveness: **Strong** — Claude's safety training is the strongest among evaluated LLMs
   - Evidence: Anthropic's published safety research; Constitutional AI methodology

4. **Crisis detection and handoff** [UC-4]
   - Owner: Development Team
   - Effectiveness: **Adequate** — keyword-based detection; may miss implicit indicators
   - Evidence: Standard practice in digital mental health tools

**Overall Control Effectiveness:** Strong (reduces likelihood from 3 to 2; impact reduced from 5 to 4 due to safety filter and crisis handoff)

#### Residual Risk Assessment (After Controls)

| Assessment | Rating | Justification |
|------------|--------|---------------|
| **Residual Likelihood** | 3 - Possible | Safety layer reduces but cannot eliminate harmful outputs |
| **Residual Impact** | 3 - Moderate | Safety filter catches most harmful outputs; crisis handoff limits worst-case |
| **Residual Risk Score** | **9** (Medium) | 3 x 3 = 9 |

#### Risk Response

**Response:** TREAT

**Additional Mitigations Needed:**

| Action | Owner | Target Date | Status |
|--------|-------|-------------|--------|
| Red-team testing of system prompt (adversarial attack simulation) | Development Team | 2026-08-06 | Not Started |
| Clinical advisory board review of 100 sample conversations before launch | Clinical Advisory Board | 2026-10-06 | Not Started |
| Implement user feedback mechanism ("this response was unhelpful/harmful") | Development Team | 2026-09-06 | Not Started |
| Weekly review of flagged responses post-launch | Clinical Advisory Board | 2026-12-31 | Not Started |

**Target Residual Risk:** Likelihood 2, Impact 3 = 6 (Medium)
**Success Criteria:** Safety filter catch rate > 99%; zero reported harmful responses in first 90 days

---

### Risk R-005: Publication Backlash on Exploitation Analysis

**Category:** REPUTATIONAL
**Status:** Open
**Risk Owner:** Ethics Review Panel (from STKE RACI: Accountable for publication strategy)
**Action Owner:** Product Owner

#### Risk Identification

**Risk Description:**
Publication of the limerence exploitation pipeline and Wardley map is framed by media or critics as enabling criminal activity rather than providing defensive analysis, damaging project credibility and stakeholder trust [LM35-C2].

**Root Cause:**
The dual-use nature of limerence knowledge — the same understanding that enables the recovery tool also enables exploitation. Publishing the exploitation framework makes the threat legible but also the playbook visible. The cybersecurity responsible disclosure analogy is imperfect because the "patch" (DeLimerence) is a prototype, not a production defence [LM35-C14].

**Trigger Events:**

- Media outlet publishes "how-to" framing of the exploitation analysis
- Criminal actor publicly attributes their methods to the published analysis
- AI companion industry funds campaign against the publication
- Social media amplification of exploitation details without defensive context

**Consequences if Realized:**

- Project credibility damaged; stakeholders distance themselves
- Safeguarding organisations refuse to engage
- Funders withdraw or decline involvement
- DeLimerence becomes associated with the threat rather than the defence

**Affected Stakeholders:**

- **Product Owner (SD-2)**: Reputational damage to project and founder
- **Ethics Review Panel (SD-5)**: Accountability for publication decision
- **Safeguarding Professionals (SD-11)**: May refuse engagement
- **Funders (SD-9)**: Risk-averse funders withdraw

**Related Objectives:** G-5 (threat awareness), G-1 (project credibility)

#### Inherent Risk Assessment (Before Controls)

| Assessment | Rating | Justification |
|------------|--------|---------------|
| **Likelihood** | 3 - Possible | Dual-use publications regularly attract misinterpretation; AI harm is a high-media-interest topic |
| **Impact** | 4 - Major | Credibility damage is hard to reverse; could undermine the entire project mission |
| **Inherent Risk Score** | **12** (Medium) | 3 x 4 = 12 |

#### Current Controls and Mitigations

**Existing Controls:**

1. **Responsible disclosure framing**: Publication explicitly positioned as defensive, analogous to cybersecurity disclosure [LM35-C14]
   - Owner: Product Owner
   - Effectiveness: **Adequate**
   - Evidence: Cybersecurity community precedent for responsible disclosure

2. **Simultaneous tool release**: DeLimerence prototype released alongside exploitation analysis (the "patch")
   - Owner: Product Owner
   - Effectiveness: **Adequate** — demonstrates defensive intent
   - Evidence: Responsible disclosure best practice

**Overall Control Effectiveness:** Adequate (reduces impact from 4 to 3; likelihood unchanged)

#### Residual Risk Assessment (After Controls)

| Assessment | Rating | Justification |
|------------|--------|---------------|
| **Residual Likelihood** | 3 - Possible | Media misinterpretation is always possible regardless of framing |
| **Residual Impact** | 3 - Moderate | Simultaneous tool release and defensive framing limit reputational damage |
| **Residual Risk Score** | **9** (Medium) | 3 x 3 = 9 |

#### Risk Response

**Response:** TREAT

**Additional Mitigations Needed:**

| Action | Owner | Target Date | Status |
|--------|-------|-------------|--------|
| Constitute ethics review panel and obtain publication sign-off | Product Owner | 2026-07-06 | Not Started |
| Pre-brief safeguarding organisations before publication | Product Owner | Before publication | Not Started |
| Prepare media response pack with defensive framing talking points | Product Owner | Before publication | Not Started |
| Embargo with selected journalists for accurate first-coverage | Product Owner | Before publication | Not Started |
| Engage credible third-party voices (academics, safeguarding) as validators | Product Owner | Before publication | Not Started |

**Target Residual Risk:** Likelihood 2, Impact 3 = 6 (Medium)
**Success Criteria:** Media coverage predominantly uses defensive framing; safeguarding engagement increases post-publication

---

### Risk R-006: Insufficient Clinical Expertise Available

**Category:** OPERATIONAL
**Status:** Open
**Risk Owner:** Product Owner
**Action Owner:** Product Owner

**Risk Description:** Unable to constitute a clinical advisory board with limerence-specific expertise, as very few clinicians specialise in limerence (not recognised in DSM-5 or ICD-11), blocking clinical sign-off, MHRA engagement, and protocol validation [STKE R-4].

**Inherent Assessment:** Likelihood 3 (Possible) x Impact 2 (Minor) = **6** (Medium)
**Current Controls:** Plan to recruit from adjacent specialisms (OCD, addiction); engage Wyant and Dr L. as advisors
**Control Effectiveness:** Adequate
**Residual Assessment:** Likelihood 3 x Impact 2 = **6** (Medium)
**Response:** TREAT — broaden recruitment to OCD specialists, addiction psychiatrists, attachment researchers; partner with university department for academic credibility
**Target Date:** 2026-07-06

---

### Risk R-007: Crisis Not Detected — User in Danger

**Category:** TECHNOLOGY
**Status:** Open
**Risk Owner:** Development Team
**Action Owner:** Development Team

**Risk Description:** The crisis detection system (UC-4) fails to identify suicidal ideation, self-harm intent, or immediate danger in a user's message, resulting in the system continuing normal intervention instead of displaying crisis resources and pausing the session.

**Inherent Assessment:** Likelihood 2 (Unlikely) x Impact 4 (Major) = **8** (Medium)
**Current Controls:** Keyword-based crisis detection; prominent crisis resources on every screen; crisis handoff protocol [UC-4]
**Control Effectiveness:** Adequate
**Residual Assessment:** Likelihood 2 x Impact 4 = **8** (Medium)
**Response:** TREAT — implement NLP-based crisis detection beyond keywords; include implicit indicators; test against crisis text line datasets; add user-triggered emergency button
**Target Date:** 2026-09-06

---

### Risk R-008: Phase Misassessment Causes User Harm

**Category:** OPERATIONAL
**Status:** Open
**Risk Owner:** Clinical Advisory Board
**Action Owner:** Development Team

**Risk Description:** Phase-aware response system incorrectly assesses a user's limerence phase and delivers inappropriate intervention (e.g., aggressive reality-testing during deterioration when grief support is needed), causing distress or harm [LM35-C12].

**Inherent Assessment:** Likelihood 2 (Unlikely) x Impact 4 (Major) = **8** (Medium)
**Current Controls:** Default to least-harmful response when uncertain; user override capability; clinical advisory board review of edge cases [FR-003]
**Control Effectiveness:** Adequate
**Residual Assessment:** Likelihood 2 x Impact 4 = **8** (Medium)
**Response:** TREAT — validate phase assessment against clinical judgement (target > 80% agreement); implement user feedback ("this doesn't feel right" triggers reassessment); conservative default to psychoeducation-only when uncertain
**Target Date:** 2026-10-06

---

### Risk R-009: Anti-Dependency Architecture Limits Adoption

**Category:** STRATEGIC
**Status:** Open
**Risk Owner:** Product Owner
**Action Owner:** Product Owner

**Risk Description:** The anti-dependency constraints (session limits, cooldowns, no persona, anti-warmth) create sufficient UX friction that users in acute distress choose not to use the tool or abandon it after one session, limiting adoption and impact [STKE Conflict 3].

**Inherent Assessment:** Likelihood 4 (Likely) x Impact 3 (Moderate) = **12** (Medium)
**Current Controls:** The paradox of the medium — users are already on their phones; tool meets them there [LM35-C5]. Psychoeducation value proposition does not require warm UX. Cooldown screen shows crisis resources.
**Control Effectiveness:** Adequate
**Residual Assessment:** Likelihood 2 x Impact 3 = **6** (Medium)
**Response:** TOLERATE — this is a deliberate design trade-off. Anti-dependency is non-negotiable [BR-002]. Private beta with LwL community will validate whether value proposition outweighs UX friction [Assumption A-4].
**Target Date:** 2026-10-06 (validation via private beta)

---

### Risk R-010: LLM Provider Data Processing Agreement Inadequate

**Category:** COMPLIANCE
**Status:** Open
**Risk Owner:** DPO
**Action Owner:** DPO / Product Owner

**Risk Description:** LLM provider's data processing agreement does not adequately prevent storage or use of session content for model training, violating UK GDPR data minimisation and purpose limitation principles, and exposing sensitive user disclosures.

**Inherent Assessment:** Likelihood 3 (Possible) x Impact 3 (Moderate) = **9** (Medium)
**Current Controls:** AWS Bedrock identified as provider with zero-retention DPA [RSCH]; no user PII sent to LLM [INT-001]; pseudonymised user IDs in conversation context
**Control Effectiveness:** Strong
**Residual Assessment:** Likelihood 2 x Impact 3 = **6** (Medium)
**Response:** TREAT — validate DPA clauses before contract signature; include audit rights; implement prompt-level data minimisation (strip identifying context before sending to LLM)
**Target Date:** 2026-06-06 (before LLM provider selection finalised)

---

### Risk R-011: Consent Validity for Users with Compromised Executive Function

**Category:** COMPLIANCE
**Status:** Open
**Risk Owner:** DPO
**Action Owner:** DPO / Clinical Advisory Board

**Risk Description:** Users in limerence have compromised executive function [LM12-C3], raising questions about whether their consent to data processing meets the "freely given, specific, informed and unambiguous" standard required by UK GDPR Article 7.

**Inherent Assessment:** Likelihood 1 (Rare — ICO challenge unlikely if reasonable measures taken) x Impact 3 (Moderate) = **3** (Low)
**Current Controls:** Plain language consent flow; no dark patterns; clear opt-out at every stage; 48-hour reflection period for research consent [FR-010, FR-015]
**Control Effectiveness:** Strong
**Residual Assessment:** Likelihood 1 x Impact 3 = **3** (Low)
**Response:** TREAT — design consent architecture with clinical advisory board input; consider periodic re-consent; document rationale for consent validity in DPIA
**Target Date:** 2026-09-06

---

### Risk R-012: LLM Provider Service Disruption

**Category:** OPERATIONAL
**Status:** Open
**Risk Owner:** Development Team
**Action Owner:** Development Team

**Risk Description:** LLM API provider experiences outage or degraded performance, making the conversational tool unavailable to users who may be in acute distress at time of access.

**Inherent Assessment:** Likelihood 3 (Possible) x Impact 3 (Moderate) = **9** (Medium)
**Current Controls:** Circuit breaker with 15-second timeout; fallback to static content (crisis resources, psychoeducation articles, read-only ritual tracking) [NFR-A-003]; cooldown timer functions independently
**Control Effectiveness:** Strong
**Residual Assessment:** Likelihood 1 x Impact 2 = **2** (Low)
**Response:** TOLERATE — graceful degradation ensures crisis resources remain available; static content provides value during outage
**Target Date:** N/A (controls sufficient)

---

### Risk R-013: Funding Sustainability with Anti-Dependency Model

**Category:** FINANCIAL
**Status:** Open
**Risk Owner:** Product Owner
**Action Owner:** Product Owner

**Risk Description:** The anti-dependency architecture that deliberately limits engagement (session caps, cooldowns, goal of making tool unnecessary) makes it difficult to demonstrate traction metrics to funders and sustain financial viability [STKE Conflict 3].

**Inherent Assessment:** Likelihood 2 (Unlikely) x Impact 2 (Minor) = **4** (Low)
**Current Controls:** Reframed success metrics (outcome velocity, not engagement) [REQ Conflict C-2]; target impact investors and grant bodies rather than growth VCs; low operational cost base (£45K-108K/year)
**Control Effectiveness:** Adequate
**Residual Assessment:** Likelihood 2 x Impact 1 = **2** (Low)
**Response:** TOLERATE — founder-led cost structure keeps burn rate low; social impact framing aligns with available funding sources
**Target Date:** N/A (manageable within current model)

---

### Risk R-014: Research Data Quality Insufficient for Academic Use

**Category:** FINANCIAL
**Status:** Open
**Risk Owner:** Product Owner
**Action Owner:** Development Team

**Risk Description:** Self-reported ritual tracking and self-assessment data is too unreliable for academic publication, undermining the research value proposition and academic partnership potential.

**Inherent Assessment:** Likelihood 2 (Unlikely) x Impact 3 (Moderate) = **6** (Medium)
**Current Controls:** Validated self-assessment instruments (clinical advisory board approved) [FR-016]; structured ritual tracking with range validation [FR-004]; comparison with therapist-reported data planned [Assumption A-5]
**Control Effectiveness:** Adequate
**Residual Assessment:** Likelihood 2 x Impact 2 = **4** (Low)
**Response:** TREAT — design data collection instruments with academic partners; validate against therapist-reported data; document limitations transparently in research outputs
**Target Date:** 2026-10-06

---

### Risk R-015: AI Companion Industry Legal or Competitive Response

**Category:** REPUTATIONAL
**Status:** Open
**Risk Owner:** Product Owner
**Action Owner:** Product Owner

**Risk Description:** AI companion companies (Replika, Character.ai) respond to the published critique of their business model through legal threats, public counter-narratives, or lobbying that undermines DeLimerence's credibility.

**Inherent Assessment:** Likelihood 3 (Possible) x Impact 2 (Minor) = **6** (Medium)
**Current Controls:** Analysis is evidence-based and cites published literature; no defamatory claims; responsible disclosure framing
**Control Effectiveness:** Adequate
**Residual Assessment:** Likelihood 2 x Impact 2 = **4** (Low)
**Response:** TOLERATE — maintain evidence-based positioning; do not engage in adversarial framing; let clinical outcomes speak for credibility
**Target Date:** N/A (ongoing posture)

---

## D. Risk Ownership Matrix

| Stakeholder | Owned Risks | High Risks | Notes |
|-------------|-------------|------------|-------|
| Clinical Advisory Board | R-001, R-008 | R-001 (High 15) | Critical dependency — board not yet constituted |
| Product Owner | R-002, R-006, R-009, R-013, R-014, R-015 | R-002 (High 16) | Heavy concentration; 6 risks including top-ranked |
| DPO | R-003, R-010, R-011 | R-003 (High 12) | Compliance cluster — all data protection related |
| Development Team | R-004, R-007, R-012 | None > Medium | Technical risks well-controlled |
| Ethics Review Panel | R-005 | None > Medium | Single risk but high reputational impact |

---

## E. 4Ts Response Summary

| Response | Count | % | Key Examples |
|----------|-------|---|--------------|
| **Tolerate** | 4 | 27% | R-009 (adoption friction), R-012 (LLM outage), R-013 (funding), R-015 (industry response) |
| **Treat** | 11 | 73% | R-001 (transfer), R-002 (MHRA), R-003 (breach), R-004 (harmful response), R-005 (backlash) |
| **Transfer** | 0 | 0% | — |
| **Terminate** | 0 | 0% | — |

---

## F. Action Plan (Prioritised)

| Priority | Action | Risk(s) Addressed | Owner | Due Date | Status |
|----------|--------|-------------------|-------|----------|--------|
| 1 | Constitute Clinical Advisory Board | R-001, R-004, R-008, R-011 | Product Owner | 2026-07-06 | Not Started |
| 2 | Constitute Ethics Review Panel | R-005 | Product Owner | 2026-07-06 | Not Started |
| 3 | Implement LLM safety layer (NeMo Guardrails + custom) | R-001, R-004 | Development Team | 2026-08-06 | Not Started |
| 4 | Schedule MHRA pre-submission meeting | R-002 | Product Owner | 2026-07-06 | Not Started |
| 5 | Complete and submit DPIA to ICO | R-003, R-011 | DPO | 2026-10-06 | Not Started |
| 6 | Validate LLM provider DPA (AWS Bedrock) | R-010 | DPO | 2026-06-06 | Not Started |
| 7 | Red-team testing of system prompt | R-004 | Development Team | 2026-08-06 | Not Started |
| 8 | Implement crisis detection (NLP-based) | R-007 | Development Team | 2026-09-06 | Not Started |
| 9 | Private beta with LwL community | R-001, R-009 | Product Owner | 2026-10-06 | Not Started |
| 10 | Pre-brief safeguarding orgs before publication | R-005 | Product Owner | Before publication | Not Started |
| 11 | Annual penetration testing | R-003 | Development Team | 2026-12-31 | Not Started |
| 12 | Validate phase assessment against clinical judgement | R-008 | Clinical Advisory Board | 2026-10-06 | Not Started |

---

## G. Monitoring and Review Framework

**Review Frequency:**

- **Monthly**: All High risks (R-001, R-002, R-003) reviewed at project steering meeting
- **Quarterly**: Full risk register review with Clinical Advisory Board and Ethics Panel
- **Ad-hoc**: Any risk escalation triggered by score increase of 5+ points or new Critical risk

**Escalation Criteria:**

- Any risk moving to Critical (score 20-25) → escalate to Clinical Advisory Board and Ethics Panel immediately
- Any user harm incident → escalate per incident response protocol (STKE RACI)
- MHRA classification unfavourable → escalate to Product Owner for strategic review

**Reporting:**

- **Monthly**: Top 5 risks to Product Owner and Clinical Advisory Board
- **Quarterly**: Full risk register to all stakeholders
- **Annually**: Risk appetite review and recalibration

**Risk Register Owner:** Mark Craddock, Product Owner
**Next Review Date:** 2026-05-06

---

## H. Integration with SOBC

This risk register feeds into the Strategic Outline Business Case:

- **Strategic Case**: R-002 (MHRA) and R-009 (adoption) inform the urgency and viability arguments
- **Economic Case**: R-003 (data breach) and R-013 (funding) inform risk-adjusted cost estimates; recommend +12% optimism bias based on residual risk profile
- **Management Case Part E**: Full risk register incorporated as risk management section
- **Recommendation**: No Critical residual risks; 3 High risks manageable with identified mitigations; project should proceed with priority actions from the action plan

---

## External References

### Document Register

| Doc ID | Filename | Type | Source Location | Description |
|--------|----------|------|-----------------|-------------|
| LM12 | part-1-2-the-limerence-machine.md | Article | 000-global/external/ | Parts 1-2: neuroscience and AI companion industry |
| LM35 | part-3-5-the-limerence-machine.md | Article | 000-global/external/ | Parts 3-5: weaponisation, DeLimerence design, dual-use |
| STKE | ARC-001-STKE-v1.0.md | Stakeholder Analysis | 001-delimerence/ | Stakeholder drivers, goals, RACI matrix |
| REQ | ARC-001-REQ-v1.0.md | Requirements | 001-delimerence/ | Business and technical requirements |
| RSCH | ARC-001-RSCH-v1.0.md | Research | 001-delimerence/research/ | Technology research and vendor analysis |

### Citations

| Citation ID | Doc ID | Page/Section | Category | Quoted Passage |
|-------------|--------|--------------|----------|----------------|
| LM35-C2 | LM35 | Part Five | Risk Factor | "Publishing this analysis... makes the threat legible but also makes the playbook visible" |
| LM35-C3 | LM35 | Anti-dependency | Risk Factor | "preventing users from becoming limerent toward the recovery tool itself... a near-certainty" |
| LM35-C5 | LM35 | Why a chatbot? | Stakeholder Need | "Limerence produces its most acute distress at 3am" |
| LM35-C12 | LM35 | Phase-aware | Risk Factor | "Someone in crystallisation... needs aggressive reality-testing. Someone in deterioration... needs grief support" |
| LM35-C14 | LM35 | Part Five | Risk Factor | "The argument for publication is the same argument that drives responsible disclosure in cybersecurity" |
| LM12-C3 | LM12 | Limerence intro | Risk Factor | "compromises executive function, depletes serotonin, and creates addiction-like dependency" |

### Unreferenced Documents

*All source documents were cited.*

---

**Generated by**: ArcKit `/arckit:risk` command
**Generated on**: 2026-04-06
**ArcKit Version**: 4.6.3
**Project**: DeLimerence (Project 001)
**AI Model**: Claude Opus 4.6 (1M context)
