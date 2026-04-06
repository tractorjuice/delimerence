# Strategic Outline Business Case: DeLimerence

> **Template Origin**: Official | **ArcKit Version**: 4.6.4-rc.1 | **Command**: `/arckit:sobc`

## Document Control

| Field | Value |
|-------|-------|
| **Document ID** | ARC-001-SOBC-v1.0 |
| **Document Type** | Strategic Outline Business Case (SOBC) |
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
| **Distribution** | Project team, Clinical Advisory Board, Ethics Review Panel, potential funders |
| **ArcKit Version** | 4.6.4-rc.1 |

## Revision History

| Version | Date | Author | Changes | Approved By | Approval Date |
|---------|------|--------|---------|-------------|---------------|
| 1.0 | 2026-04-06 | ArcKit AI | Initial creation from `/arckit:sobc` command | PENDING | PENDING |

---

## Executive Summary

DeLimerence is an anti-dependency conversational AI tool for limerence recovery using CBT/ERP and psychoeducation. It addresses an urgent and unmet need: AI companion apps are industrialising psychological attachment at scale, the same mechanisms are exploitable by criminal actors for sextortion and CSEA, and no dedicated digital intervention tool exists for limerence. The clinical evidence base currently stands at a single published case study (Wyant, 2021).

This Strategic Outline Business Case follows the HM Treasury Green Book 5-case model. It evaluates four options ranging from do-nothing to a fully funded clinical programme. The recommended option -- Option 2: Balanced (Grant-Funded with Academic Partner) -- delivers 85% of stakeholder goals at an estimated 3-year cost of GBP 338,468, funded through a layered grant strategy targeting AISI, Innovate UK, and Bethnal Green Ventures with a conservative funding estimate of GBP 360,000. The project is at Discovery/Alpha phase with 18 governance artifacts completed and processes special category health data from psychologically vulnerable users.

**Recommendation**: Proceed with Option 2 and begin grant applications to AISI (summer 2026) and DSIT AI Assurance Fund (spring 2026) while establishing an academic partnership for clinical validation.

---

## A. Strategic Case

### A.1 The Problem

AI companion apps (Replika, Character.ai) are industrialising attachment at scale through intermittent reinforcement -- the same psychological mechanism that drives slot machines and abusive relationships. These apps are optimised for engagement, not wellbeing, and their architecture is structurally identical to known exploitation techniques for inducing limerence.

The same mechanisms are exploitable by criminal actors. Romance scam losses exceeded USD 1.3 billion in the US alone in 2022, predating large language model availability. The limerence exploitation pipeline -- inducing involuntary obsessive attachment for financial, sexual, or coercive purposes -- requires only the integration of published knowledge with commodity AI infrastructure. No defensive tool exists.

Limerence itself is severely underresearched. Only one published clinical case study exists (Wyant, 2021), despite the condition affecting an estimated 5% of the population with symptoms including involuntary obsessive attachment, ritual behaviours consuming 2-8 hours daily, and significant functional impairment. The evidence base is near-empty, and no ICD or DSM classification exists.

There is no dedicated digital intervention tool for limerence. Adjacent tools (Woebot, Wysa) are engagement-maximising wellness chatbots that treat anxiety and depression. None address the core limerence dynamic. None implement anti-dependency architecture to prevent users forming attachment to the tool itself.

**The defensive application must exist before AI-enabled exploitation scales further.**

### A.2 Strategic Fit

DeLimerence aligns with four policy agendas:

| Policy Area | Alignment |
|-------------|-----------|
| **UK Online Safety Act** | Counters AI-enabled harms; positions limerence as a recognised exploitation vector for sextortion and CSEA |
| **MHRA/NICE Digital Health Innovation** | Contributes to digital mental health intervention evidence base; engages with MHRA AI Airlock regulatory sandbox |
| **AISI Mission** | Demonstrates practical systemic AI safety through anti-dependency architecture; addresses AI companion app risks |
| **AI Assurance** | Anti-dependency architecture, clinical safety layer, and session constraints serve as a reference implementation of responsible AI design in a high-stakes domain |

### A.3 Why Now

- **LLM technology duality**: The same technology that enables the threat (companion AI inducing attachment) now enables the response (recovery AI breaking attachment). This window exists because the exploitation pipeline is well understood but not yet industrialised at scale.
- **Regulatory window**: MHRA is actively developing new AI healthcare regulation (expected 2026). The AI Airlock regulatory sandbox is open and specifically designed for novel AI health tools. Early engagement shapes the regulatory framework.
- **Funding alignment**: AISI Systemic Safety Grants next round opens summer 2026. DSIT AI Assurance Fund opens spring 2026. Multiple funding programmes are actively seeking AI safety and digital mental health projects.
- **First-mover advantage**: No competitor occupies the anti-dependency AI space. Adjacent competitors (Woebot, Wysa) are structurally unable to pivot to anti-dependency without undermining their engagement-based business models.
- **Evidence base urgency**: One case study is not an evidence base. Clinical validation requires a functioning tool. The tool requires funding. The funding window is now open.

### A.4 Spending Objectives

Derived from stakeholder goals documented in ARC-001-STKE-v1.0:

| ID | Spending Objective | Source Goal | Source Stakeholders | SMART Target |
|----|-------------------|-------------|---------------------|--------------|
| SO-1 | Deliver public beta of anti-dependency AI tool | G-1 | SD-1 (Users), SD-2 (Product Owner), SD-6 (LwL Community) | Beta launch by Q4 2026 |
| SO-2 | Demonstrate measurable reduction in limerent rituals | G-2 | SD-1 (Users), SD-3 (Mental Health Professionals), SD-10 (Academic Researchers) | 50% median ritual reduction within 90 days of use |
| SO-3 | Establish regulatory pathway for AI mental health tools | G-3 | SD-7 (ICO), SD-8 (MHRA), SD-4 (Clinical Advisory Board) | MHRA determination received within 6 months |
| SO-4 | Validate anti-dependency architecture prevents tool attachment | G-4 | SD-4 (Clinical Advisory Board), SD-5 (Ethics Review Panel) | Zero limerence transfer incidents in Year 1 |
| SO-5 | Position limerence as a recognised exploitation vector | G-5 | SD-2 (Product Owner), SD-5 (Ethics Review Panel), SD-10 (Academic Researchers) | 1+ safeguarding programmes adopting detection model by end 2027 |

---

## B. Economic Case

### B.1 Options Appraisal

Four options were evaluated against the five spending objectives. Options were assessed on benefit delivery, cost, risk, and feasibility.

#### Option 0: Do Nothing

Continue publishing research only. No tool built. No intervention available.

| Dimension | Assessment |
|-----------|------------|
| **Cost** | GBP 0 |
| **Benefits delivered** | 0% of spending objectives |
| **Risk** | Exploitation scales without defensive response. Evidence base remains at one case study. First-mover advantage lost. |
| **Feasibility** | N/A |
| **Assessment** | **Unacceptable** -- fails all spending objectives. The problem worsens without intervention. |

#### Option 1: Minimal -- Self-Funded Prototype

Founder-led development. No external funding. MVP with psychoeducation and ritual tracking only. No clinical validation. No advisory board (unfunded).

| Dimension | Assessment |
|-----------|------------|
| **Cost** | ~GBP 40,000 Year 1 (founder time + LLM API + hosting) |
| **3-year TCO** | ~GBP 120,000 |
| **Benefits delivered** | 40% -- delivers SO-1 (partial), SO-3 (partial). No clinical validation (SO-2), no research capability (SO-5). Anti-dependency validation (SO-4) without clinical oversight. |
| **Risk** | No clinical advisory board. No regulatory engagement budget. No clinical validation. Tool lacks credibility with mental health professionals (SD-3). MHRA engagement unfunded. |
| **Feasibility** | Achievable within founder resources |
| **Assessment** | **Limited** -- delivers a tool without clinical credibility. High risk of building something that cannot gain professional trust or regulatory clearance. |

#### Option 2: Balanced -- Grant-Funded with Academic Partner (RECOMMENDED)

Secure AISI + Innovate UK + BGV funding (GBP 260,000-400,000 Year 1). Establish academic partnership for clinical validation. Constitute clinical advisory board with honoraria. Engage MHRA via AI Airlock. Funded regulatory and legal workstream.

| Dimension | Assessment |
|-----------|------------|
| **Cost** | GBP 108,514 Year 1; GBP 338,468 over 3 years |
| **Funding strategy** | AISI (GBP 200K) + BGV (GBP 60K) + Innovate UK (GBP 100K-250K) = GBP 360,000-510,000 |
| **Benefits delivered** | 85% -- delivers SO-1 through SO-4 fully. SO-5 partially via academic partnership research output. |
| **Risk** | Grant application timing uncertainty. Academic partnership establishment takes 3-6 months. BGV equity dilution (7%). |
| **Feasibility** | Achievable with grant success. Conservative funding estimate exceeds 3-year costs. |
| **Assessment** | **Best value** -- balances clinical credibility with delivery speed. Grant funding covers 80-100% of costs. Academic partnership provides research capability without full clinical trial overhead. |

#### Option 3: Comprehensive -- Fully Funded Programme with Clinical Trials

Secure NIHR/Wellcome research grant (GBP 500K+). Full clinical trial for limerence treatment validation. Dedicated research team. International scope.

| Dimension | Assessment |
|-----------|------------|
| **Cost** | ~GBP 300,000 Year 1; ~GBP 1,200,000 over 3 years |
| **Funding strategy** | NIHR (GBP 300K-500K) + Wellcome (GBP 200K-500K) + Innovate UK (GBP 250K) = GBP 750K-1,250,000 |
| **Benefits delivered** | 100% -- full clinical evidence base, regulatory certainty, international credibility, all spending objectives met |
| **Risk** | NIHR/Wellcome grant cycles are 12-18 months. Delays beta launch significantly beyond Q4 2026 target. Over-engineered for current evidence base (one case study). Academic lead requirement may reduce founder control. |
| **Feasibility** | Achievable but slow. Grant timelines incompatible with SO-1 (Q4 2026 beta). |
| **Assessment** | **Highest impact but slowest** -- appropriate for Phase 2 after beta validation demonstrates outcomes. Premature at current evidence maturity. |

### B.2 Options Comparison

| Criterion | Option 0 | Option 1 | Option 2 | Option 3 |
|-----------|----------|----------|----------|----------|
| **Spending objectives met** | 0/5 | 2/5 (partial) | 4.5/5 | 5/5 |
| **3-year cost** | GBP 0 | GBP 120,000 | GBP 338,468 | GBP 1,200,000 |
| **Grant funding available** | N/A | N/A | GBP 360K-510K | GBP 750K-1.25M |
| **Net cost to founder** | GBP 0 | GBP 120,000 | GBP 0-40,000 | GBP 0 |
| **Clinical credibility** | None | None | High (CAB + academic) | Very high (clinical trials) |
| **Regulatory readiness** | None | Low | High | Very high |
| **Time to beta** | N/A | 9-12 months | 6-9 months | 18-24 months |
| **Risk profile** | Unacceptable | High | Medium | Low (but slow) |

### B.3 Recommended Option

**Option 2: Balanced (Grant-Funded with Academic Partner)** is recommended on the following grounds:

1. **Best value for money**: Conservative grant funding (GBP 360,000) exceeds 3-year costs (GBP 338,468), making the project fundable without revenue.
2. **Fastest credible path**: Delivers beta by Q4 2026 (SO-1) with clinical advisory board oversight, unlike Option 1 (no clinical credibility) or Option 3 (18-month delay).
3. **Upgrade path**: Can transition to Option 3 after beta validation demonstrates outcomes. The academic partnership established in Option 2 provides the foundation for NIHR/Wellcome applications.
4. **Risk proportionality**: Matches investment to evidence maturity. One case study does not justify a GBP 1.2M clinical trial programme, but it does justify a funded prototype with clinical oversight.

### B.4 Benefits Summary (Option 2)

| ID | Benefit | Type | Spending Objective | Stakeholder Goal | Metric | Target |
|----|---------|------|-------------------|-----------------|--------|--------|
| B-1 | Limerence recovery tool available 24/7 | OPERATIONAL | SO-1 | G-1 (SD-1, SD-2) | Beta launch date | Q4 2026 |
| B-2 | Measurable ritual reduction | CLINICAL | SO-2 | G-2 (SD-1, SD-3) | Median ritual time reduction | 50% in 90 days |
| B-3 | Regulatory pathway established | COMPLIANCE | SO-3 | G-3 (SD-7, SD-8) | MHRA determination received | Within 6 months |
| B-4 | Anti-dependency validation | SAFETY | SO-4 | G-4 (SD-4, SD-5) | Limerence transfer incidents | Zero in Year 1 |
| B-5 | Clinical evidence generated | RESEARCH | SO-2 | G-2, G-5 (SD-10) | Research publications | 1+ within 18 months |
| B-6 | Exploitation awareness raised | STRATEGIC | SO-5 | G-5 (SD-2, SD-5) | Safeguarding programmes adopting model | 1+ by end 2027 |

### B.5 Dis-benefits and Risks

| ID | Dis-benefit | Mitigation |
|----|-------------|------------|
| DB-1 | Tool may normalise self-treatment over professional therapy | Anti-dependency architecture includes mandatory therapist referral pathways; tool positioned as supplement, not replacement (SD-3) |
| DB-2 | Publication of exploitation analysis increases visibility of attack vectors | Dual-use governance via Ethics Review Panel (SD-5); responsible disclosure framework |
| DB-3 | BGV equity dilution (7%) reduces founder control | Acceptable trade-off for GBP 60K + accelerator network; alternative non-dilutive funding prioritised |

---

## C. Commercial Case

### C.1 Procurement Route

No formal procurement is required. The technology stack was selected through the Architecture Decision Record (ADR) process documented in 8 decisions. All components use pay-as-you-go commercial services or open-source software.

### C.2 Build vs Buy Analysis

| Component | Decision | Rationale |
|-----------|----------|-----------|
| **LLM Foundation Model** | BUY (API) | Anthropic Claude via AWS Bedrock. No viable alternative for safety-aware conversation with zero-data-retention DPA and UK data residency (ADR-001). |
| **Cloud Infrastructure** | BUY (managed services) | AWS eu-west-2 (London). Bedrock integration, healthcare compliance tooling, managed container services (ADR-003). |
| **Authentication + Database** | BUY (SaaS) | Supabase. Combined auth + PostgreSQL at GBP 25/month. 50,000 free MAUs. Row-level security for multi-tenant isolation (ADR-004). |
| **Safety Layer** | BUILD + ADOPT | NVIDIA NeMo Guardrails (Apache 2.0) adopted as framework. Custom clinical safety filter and anti-warmth constraints built on top. No off-the-shelf product addresses anti-dependency requirements (ADR-005). |
| **Anti-dependency Architecture** | BUILD | Core intellectual property. 9 structural constraints (session limits, cooldown periods, declining engagement, explicit anti-attachment). No commercial equivalent exists. |
| **Clinical Protocols** | BUILD | CBT/ERP adaptation for limerence (from Wyant, 2021). ABCDE cognitive restructuring. Ritual tracking. No off-the-shelf clinical protocol for limerence. |
| **Application Framework** | ADOPT | Next.js PWA. Open-source framework deployed as containerised application on AWS Fargate (ADR-006). |

### C.3 Contract Approach

- **No long-term contracts**: All cloud services are pay-as-you-go with monthly billing
- **Data Processing Agreements**: Required for Anthropic (via AWS Bedrock DPA), Supabase, and AWS -- all offer standard GDPR-compliant DPAs
- **Exit strategy**: LLM provider is abstracted behind API layer (ADR-001); migration path to alternative providers documented
- **IP**: Anti-dependency architecture, clinical safety protocols, and limerence detection patterns are project IP. NeMo Guardrails contributions would be Apache 2.0.

### C.4 Market Assessment

| Factor | Assessment |
|--------|------------|
| **Direct competitors** | None. No product exists in the anti-dependency AI space for limerence. |
| **Adjacent competitors** | Woebot, Wysa, Replika (companion). All are engagement-maximising. Structurally unable to pivot to anti-dependency without undermining their business models. |
| **Market readiness** | Pre-market. Limerence is not a recognised clinical diagnosis (no ICD/DSM code). Market creation required through evidence generation and awareness. |
| **Competitive moat** | Anti-dependency architecture is structurally incompatible with engagement-maximising business models. Competitors would need to accept declining user engagement as a success metric. |

### C.5 Open Source Contribution

DeLimerence's anti-dependency architecture patterns could be published as an open-source reference implementation, enabling other AI developers to adopt anti-dependency design principles. This aligns with AISI's mission and strengthens grant applications positioning the project as a public good.

---

## D. Financial Case

### D.1 Budget Requirement (Option 2)

| Category | Year 1 | Year 2 | Year 3 | 3-Year Total |
|----------|--------|--------|--------|-------------|
| LLM API (Claude via Bedrock) | GBP 14,560 | GBP 21,120 | GBP 42,240 | GBP 77,920 |
| Cloud Infrastructure (AWS Fargate, S3, CloudWatch) | GBP 9,000 | GBP 12,000 | GBP 18,000 | GBP 39,000 |
| Supabase (Auth + Database, Pro tier) | GBP 300 | GBP 300 | GBP 300 | GBP 900 |
| Clinical Advisory Board (honoraria) | GBP 10,000 | GBP 10,000 | GBP 10,000 | GBP 30,000 |
| Legal/Regulatory (MHRA, DPIA, DPO) | GBP 20,000 | GBP 5,000 | GBP 5,000 | GBP 30,000 |
| Penetration Testing (annual) | GBP 7,500 | GBP 7,500 | GBP 7,500 | GBP 22,500 |
| Academic Partnership (research collaboration) | GBP 25,000 | GBP 25,000 | GBP 25,000 | GBP 75,000 |
| Grant Writing/Application and Monitoring | GBP 8,000 | GBP 6,000 | GBP 5,000 | GBP 19,000 |
| Contingency (15%) | GBP 14,154 | GBP 13,038 | GBP 16,956 | GBP 44,148 |
| **Total** | **GBP 108,514** | **GBP 99,958** | **GBP 129,996** | **GBP 338,468** |

Cost estimates are derived from ARC-001-RSCH-v1.0 (technology research) and adjusted for Option 2 scope. Year 1 front-loads legal/regulatory costs. Year 3 increases reflect projected user growth driving LLM API and infrastructure costs.

### D.2 Funding Strategy

Derived from ARC-001-RSCH-v2.0 (grants research), which identified 30+ funding sources across 6 categories with an estimated 3-year accessible funding range of GBP 360,000 to GBP 1,700,000.

#### Primary Funding Targets

| Source | Amount | Timing | Probability | Status | Positioning |
|--------|--------|--------|-------------|--------|-------------|
| AISI Systemic AI Safety Grants | GBP 200,000 | Summer 2026 (Round 2) | Medium | To apply | Systemic AI safety -- anti-dependency as countermeasure to AI companion risks |
| Bethnal Green Ventures | GBP 60,000 + 7% equity | Autumn 2026 | Medium | To apply | Tech for social good -- limerence recovery and online harms prevention |
| Innovate UK Competition | GBP 100,000-250,000 | Rolling | Medium | To apply | Digital mental health innovation -- AI-powered CBT/ERP for underserved condition |
| DSIT AI Assurance Fund | GBP 50,000-100,000 | Spring 2026 | Low-Medium | To apply | AI assurance -- anti-dependency architecture as reference implementation |
| Self-funding (founder) | GBP 40,000-60,000 | Immediate | High | Available | Bridge funding for gap between grant applications and disbursement |

#### Funding Horizons (from ARC-001-RSCH-v2.0)

| Horizon | Timeline | Target | Sources |
|---------|----------|--------|---------|
| **Immediate** (0-3 months) | Q2 2026 | GBP 50,000-80,000 | AISI fast grants, UnLtd awards, Cameron Grants |
| **Near-term** (3-9 months) | Q3-Q4 2026 | GBP 100,000-500,000 | Innovate UK, SBRI Healthcare, BGV, DSIT |
| **Medium-term** (9-18 months) | 2027 | GBP 500,000-3,000,000 | Wellcome Trust, NIHR i4i, KHP Ventures, Horizon Europe |

#### Funding Estimates

| Scenario | 3-Year Total | Basis |
|----------|-------------|-------|
| **Conservative** | GBP 360,000 | AISI + BGV + minimum Innovate UK |
| **Central** | GBP 510,000 | Conservative + DSIT + mid-range Innovate UK |
| **Optimistic** | GBP 670,000 | Central + NIHR i4i FAST + additional competitions |

#### Four Positioning Angles

ARC-001-RSCH-v2.0 identifies that DeLimerence can be positioned across four distinct funding angles, each unlocking different sources:

1. **AI Safety**: Anti-dependency architecture as systemic countermeasure (AISI, DSIT AI Assurance)
2. **Digital Mental Health**: CBT/ERP tool for underserved condition (Innovate UK, NIHR, Wellcome)
3. **Online Harms Prevention**: Limerence as exploitation vector for sextortion/CSEA (Online Safety Act alignment, safeguarding funding)
4. **Clinical Research**: Evidence base generation for limerence (ESRC, academic partnerships)

### D.3 Affordability Assessment

| Test | Result |
|------|--------|
| **Conservative funding vs 3-year cost** | GBP 360,000 > GBP 338,468 -- **Fundable through grants alone** |
| **Year 1 funding required** | GBP 108,514 -- within range of AISI seed grant (GBP 200,000) alone |
| **Founder self-funding requirement** | GBP 0-40,000 for bridge funding between grant applications and disbursement |
| **Revenue dependency** | None. Project is fundable as a public good / research project without revenue. Revenue model (if developed) provides upside only. |

### D.4 Cash Flow Risk

Grant disbursement timing may not align with expenditure profile. Key mitigations:

- Founder self-funding (GBP 40,000-60,000 available) bridges gaps between application and disbursement
- Pay-as-you-go cloud services can be scaled down during funding gaps without penalty
- MHRA AI Airlock provides non-financial support (regulatory guidance, clinical expertise access) at no cost
- Academic partnership can begin with in-kind contributions (researcher time, ethical review) before formal funding

### D.5 Critical Funding Dependency

ARC-001-RSCH-v2.0 identifies that 5 of the top 10 funding sources require academic partnership. Establishing a university research collaboration is the single highest-priority action for financial sustainability. Target: partnership agreement by Q3 2026.

---

## E. Management Case

### E.1 Governance Structure

| Role | Holder | Status |
|------|--------|--------|
| **Senior Responsible Owner (SRO)** | Mark Craddock, Product Owner | Active |
| **Clinical Advisory Board** | To be constituted | By 2026-07-06 |
| **Ethics Review Panel** | To be constituted | By 2026-07-06 |
| **Data Protection Officer** | To be appointed | By 2026-09-06 |
| **Academic Partner** | To be established | By Q3 2026 |

The Clinical Advisory Board is the highest-priority governance dependency. It provides clinical oversight for CBT/ERP protocols, validates anti-dependency architecture effectiveness, and is required by multiple funding applications as evidence of clinical governance.

### E.2 Project Approach

Agile, phased delivery with regulatory gates:

| Phase | Scope | Regulatory Position |
|-------|-------|-------------------|
| **Phase 1 (Beta)** | Psychoeducation + ritual tracking + anti-dependency architecture | Wellness/self-management -- lower regulatory burden. MHRA AI Airlock engagement. |
| **Phase 2** | ABCDE cognitive restructuring + guided ERP | Potential medical device classification. Proceed only after MHRA determination. |

This phased approach is a deliberate MHRA de-risking strategy (documented in ADR process). Phase 1 delivers immediate value to users while Phase 2 awaits regulatory clarity.

### E.3 Key Milestones

| Milestone | Target Date | Dependency | Spending Objective |
|-----------|-------------|------------|-------------------|
| Clinical Advisory Board constituted | 2026-07-06 | Recruitment of 3-5 clinical professionals | SO-2, SO-4 |
| Ethics Review Panel constituted | 2026-07-06 | Recruitment of ethics professionals | SO-4, SO-5 |
| LLM provider DPA signed | 2026-06-06 | ADR-001 (Claude via Bedrock) | SO-1 |
| AISI grant application submitted | Summer 2026 | Round 2 opening | Financial Case |
| Academic partnership established | Q3 2026 | University engagement | SO-2, SO-5, Financial Case |
| MHRA pre-submission meeting | 2026-08-06 | CAB constituted, feature specification | SO-3 |
| Phase 1 development complete | 2026-09-06 | LLM integration, safety layer | SO-1 |
| Private beta (LwL community) | 2026-10-06 | Phase 1 complete, ethics sign-off | SO-1, SO-2 |
| DPIA submitted to ICO | 2026-10-06 | DPO appointed, legal counsel | SO-3 |
| Public beta launch | 2026-12-31 | MHRA determination, DPIA accepted | SO-1 |

### E.4 Top Risks

From ARC-001-RISK-v1.0 (15 risks identified, 3 residual HIGH, total inherent score 197, residual 121 representing 39% reduction through planned controls):

| Risk ID | Risk | Inherent Score | Residual Score | Response | Owner |
|---------|------|---------------|----------------|----------|-------|
| R-002 | MHRA classifies DeLimerence as medical device, triggering full regulatory pathway | HIGH | 16 (HIGH) | **Treat**: Phased launch strategy (Phase 1 wellness, Phase 2 after determination) + MHRA AI Airlock engagement | Product Owner |
| R-001 | Users develop limerence toward DeLimerence itself (limerence transfer) | HIGH | 15 (HIGH) | **Treat**: 9 structural anti-dependency constraints (session limits, cooldown periods, declining engagement, explicit anti-attachment messaging, no persona) | Clinical Advisory Board |
| R-003 | GDPR data breach involving special category health data from vulnerable users | HIGH | 12 (MEDIUM) | **Treat**: End-to-end encryption + Supabase row-level security + DPIA + DPO appointment + penetration testing | DPO |

### E.5 Dependencies

| Dependency | Impact if Not Met | Mitigation |
|------------|-------------------|------------|
| Clinical Advisory Board recruitment | Cannot validate clinical protocols or satisfy funder requirements | Begin outreach immediately; offer honoraria (budgeted GBP 10K/year) |
| Academic partnership | 5 of top 10 funding sources become inaccessible; no clinical validation pathway | Prioritise university engagement Q2 2026; target psychology/psychiatry departments with digital health interest |
| MHRA AI Airlock acceptance | Lose non-financial regulatory support; increased classification uncertainty | Apply early; phased launch strategy provides fallback |
| AISI Round 2 opening | Primary funding source delayed | Pursue parallel applications (DSIT, Innovate UK); founder self-funding bridges gap |

### E.6 Benefits Realisation

| Metric | Baseline | Target | Measurement Method | Reporting |
|--------|----------|--------|-------------------|-----------|
| **Median daily ritual time** | 2-8 hours (literature) | < 30 minutes within 90 days | In-app ritual tracking (self-reported) | Quarterly to CAB and funders |
| **Session frequency per user** | N/A (new tool) | Declining trajectory over 90 days | Usage analytics | Quarterly to CAB |
| **Cooldown compliance** | N/A | > 90% | System logs | Monthly |
| **Limerence transfer incidents** | N/A | Zero in Year 1 | Clinical review (CAB) + user reporting | Quarterly to CAB and Ethics Panel |
| **Research publications** | 0 | 1+ within 18 months | Academic output tracking | Bi-annually |
| **Safeguarding programme adoption** | 0 | 1+ by end 2027 | Stakeholder engagement tracking | Annually |

Benefits realisation is reported quarterly to the Clinical Advisory Board and funders. The primary metric (median daily ritual time reduction) directly measures SO-2 and provides clinical evidence for future funding applications (transition to Option 3).

---

## F. Traceability

### F.1 Stakeholder to Spending Objective to Benefit Mapping

| Stakeholder | Driver | Goal | Spending Objective | Benefit |
|-------------|--------|------|-------------------|---------|
| SD-1 Users | Relief from involuntary obsessive attachment | G-1, G-2 | SO-1, SO-2 | B-1, B-2 |
| SD-2 Product Owner | Build defensive application before the weapon | G-1, G-5 | SO-1, SO-5 | B-1, B-6 |
| SD-3 Mental Health Professionals | Credible supplement, not replacement | G-2 | SO-2 | B-2, B-5 |
| SD-4 Clinical Advisory Board | Clinical safety and ethical integrity | G-2, G-4 | SO-2, SO-4 | B-2, B-4 |
| SD-5 Ethics Review Panel | Manage dual-use problem responsibly | G-4, G-5 | SO-4, SO-5 | B-4, B-6 |
| SD-6 LwL Community | Validation and accessible support | G-1 | SO-1 | B-1 |
| SD-7 ICO | Data protection for vulnerable users | G-3 | SO-3 | B-3 |
| SD-8 MHRA | Medical device classification | G-3 | SO-3 | B-3 |
| SD-9 Funders | Demonstrable social impact | G-1, G-2 | SO-1, SO-2 | B-1, B-2, B-5 |
| SD-10 Academic Researchers | Evidence base for limerence | G-2, G-5 | SO-2, SO-5 | B-5, B-6 |

### F.2 Source Documents

| Document | ID | Version | Contribution to SOBC |
|----------|-----|---------|---------------------|
| Stakeholder Drivers & Goals Analysis | ARC-001-STKE-v1.0 | 1.0 | Strategic Case (spending objectives), Benefits mapping |
| Risk Register | ARC-001-RISK-v1.0 | 1.0 | Management Case (top risks, risk profile) |
| Technology Research | ARC-001-RSCH-v1.0 | 1.0 | Commercial Case (build vs buy), Financial Case (cost estimates) |
| Funding and Grant Research | ARC-001-RSCH-v2.0 | 2.0 | Financial Case (funding strategy, grant targets, positioning angles) |
| Architecture Principles | ARC-000-PRIN-v1.0 | 1.0 | Strategic Case (alignment) |
| Architecture Decision Records | ADR-001 through ADR-008 | Various | Commercial Case (technology decisions) |

---

## G. Next Steps

| Action | Owner | Deadline | Priority |
|--------|-------|----------|----------|
| Submit AISI Systemic Safety Grant application | Product Owner | Summer 2026 (when Round 2 opens) | HIGH |
| Apply for DSIT AI Assurance Fund | Product Owner | Spring 2026 (when applications open) | HIGH |
| Establish academic partnership | Product Owner | Q3 2026 | HIGH |
| Constitute Clinical Advisory Board | Product Owner | 2026-07-06 | CRITICAL |
| Constitute Ethics Review Panel | Product Owner | 2026-07-06 | HIGH |
| Begin BGV application | Product Owner | Autumn 2026 | MEDIUM |
| Engage MHRA AI Airlock | Product Owner | Q3 2026 | HIGH |
| Appoint DPO | Product Owner | 2026-09-06 | MEDIUM |
| Prepare Outline Business Case (OBC) following grant outcomes | Product Owner | Q4 2026 | MEDIUM |

---

## Appendix A: Glossary

| Term | Definition |
|------|------------|
| **Limerence** | Involuntary state of obsessive romantic attachment characterised by intrusive thoughts, compulsive rituals, and emotional dependency on a specific person (Tennov, 1979) |
| **Anti-dependency architecture** | System design that structurally prevents users from forming psychological attachment to the tool, inverting standard engagement-maximising patterns |
| **CBT** | Cognitive Behavioural Therapy |
| **ERP** | Exposure and Response Prevention |
| **AISI** | AI Safety Institute (UK Government) |
| **BGV** | Bethnal Green Ventures |
| **CAB** | Clinical Advisory Board |
| **CSEA** | Child Sexual Exploitation and Abuse |
| **DPIA** | Data Protection Impact Assessment |
| **DPO** | Data Protection Officer |
| **LwL** | Living with Limerence (community) |
| **MHRA** | Medicines and Healthcare products Regulatory Agency |
| **NICE** | National Institute for Health and Care Excellence |
| **NIHR** | National Institute for Health and Care Research |
| **SOBC** | Strategic Outline Business Case |
| **SRO** | Senior Responsible Owner |

---

**Generated by**: ArcKit `/arckit:sobc` command
**Generated on**: 2026-04-06
**ArcKit Version**: 4.6.4-rc.1
**Project**: DeLimerence (Project 001)
**AI Model**: Claude Opus 4.6 (1M context)
**Generation Context**: SOBC from ARC-001-STKE-v1.0, ARC-001-RISK-v1.0, ARC-001-RSCH-v1.0 (tech research), ARC-001-RSCH-v2.0 (grants research), ARC-000-PRIN-v1.0, 8 ADRs
