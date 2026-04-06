# Stakeholder Drivers & Goals Analysis: DeLimerence

> **Template Origin**: Official | **ArcKit Version**: 4.6.3 | **Command**: `/arckit:stakeholders`

## Document Control

| Field | Value |
|-------|-------|
| **Document ID** | ARC-001-STKE-v1.0 |
| **Document Type** | Stakeholder Drivers & Goals Analysis |
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
| **Distribution** | Project team, clinical advisors, ethics review panel |

## Revision History

| Version | Date | Author | Changes | Approved By | Approval Date |
|---------|------|--------|---------|-------------|---------------|
| 1.0 | 2026-04-06 | ArcKit AI | Initial creation from `/arckit:stakeholders` command | PENDING | PENDING |

---

## Executive Summary

### Purpose

This document identifies key stakeholders for the DeLimerence project, their underlying drivers (motivations, concerns, needs), how these drivers manifest into goals, and the measurable outcomes that will satisfy those goals. DeLimerence is a conversational AI tool built as a deliberate inversion of the companion AI model — designed to help people recognise and recover from limerence using CBT, ERP, and psychoeducation, while preventing users from forming attachment to the tool itself [LM35-C1].

### Key Findings

The stakeholder landscape divides into three distinct clusters: **users in acute psychological distress** who need immediate, clinically sound intervention; **professional communities** (therapists, safeguarding professionals, law enforcement) who need the tool to be credible, evidence-based, and complementary to existing practice; and **regulatory and ethical bodies** who need assurance that a tool interacting with vulnerable people meets safety, data protection, and clinical governance standards. The most significant tension exists between user accessibility (available 24/7, low barrier to entry) and clinical safety (ensuring the tool does not cause harm or replace professional support). A secondary tension exists between the dual-use nature of the underlying knowledge — publishing the exploitation analysis increases awareness but also visibility of the playbook [LM35-C2].

### Critical Success Factors

- Anti-dependency architecture is demonstrably effective at preventing user attachment to the tool [LM35-C3]
- Clinical framework (CBT/ERP adapted from Wyant, 2021) produces measurable reduction in limerent rituals [LM35-C4]
- Tool achieves trust from mental health professionals as a credible supplement (not replacement) for therapy
- Regulatory compliance (data protection, potential medical device classification) is established before public launch
- Safeguarding community recognises limerence as an attack vector and adopts the detection framework

### Stakeholder Alignment Score

**Overall Alignment**: MEDIUM

Strong alignment exists between the product vision and the needs of users, therapists, and safeguarding professionals. Tension points include: clinical governance requirements may slow time-to-market; the anti-dependency architecture deliberately limits engagement metrics that would otherwise demonstrate traction to funders; and the dual-use disclosure creates reputational risk if the exploitation framework is misinterpreted as enabling rather than defensive.

---

## Stakeholder Identification

### Internal Stakeholders

| Stakeholder | Role/Department | Influence | Interest | Engagement Strategy |
|-------------|----------------|-----------|----------|---------------------|
| Product Owner (Mark Craddock) | Founder / Architect | HIGH | HIGH | Active involvement, all strategic decisions |
| Clinical Advisory Board | Clinical Governance | HIGH | HIGH | Protocol review, safety sign-off, ongoing supervision |
| Development Team | Engineering | MEDIUM | HIGH | Sprint planning, architecture decisions, implementation |
| Ethics Review Panel | Ethics & Safety | HIGH | HIGH | Pre-launch review, ongoing dual-use monitoring |
| UX / Content Design | Design | MEDIUM | HIGH | Anti-dependency UX patterns, psychoeducation content |
| Data Protection Officer | Compliance | HIGH | MEDIUM | DPIA, consent architecture, data minimisation |

### External Stakeholders

| Stakeholder | Organization | Relationship | Influence | Interest |
|-------------|--------------|--------------|-----------|----------|
| People experiencing limerence | General public | Primary users | LOW | HIGH |
| Mental health professionals | Therapists, counsellors, psychiatrists | Referral partners | HIGH | HIGH |
| Living with Limerence community | Online community (Dr L.) | Peer support ecosystem | MEDIUM | HIGH |
| Safeguarding professionals | Local authorities, charities | Detection/intervention adopters | MEDIUM | HIGH |
| Law enforcement | Police, NCA | Intelligence consumers | MEDIUM | MEDIUM |
| Platform operators | Dating apps, social media | Detection mechanism adopters | HIGH | MEDIUM |
| Regulators (ICO) | Information Commissioner's Office | Data protection oversight | HIGH | MEDIUM |
| Regulators (MHRA) | Medicines & Healthcare products Regulatory Agency | Medical device classification | HIGH | MEDIUM |
| Children's safeguarding orgs | NSPCC, IWF, CEOP | Child protection advocacy | MEDIUM | HIGH |
| Academic researchers | Universities, clinical psychology | Evidence base, validation | MEDIUM | HIGH |
| Funders / Impact investors | Social impact / health tech | Financial sustainability | HIGH | MEDIUM |
| AI companion industry | Replika, Character.ai et al. | Subject of critique | HIGH | LOW |

### Stakeholder Power-Interest Grid

```text
                          INTEREST
              Low                         High
        ┌─────────────────────┬─────────────────────┐
        │                     │                     │
        │   KEEP SATISFIED    │   MANAGE CLOSELY    │
   High │                     │                     │
        │  • ICO              │  • Product Owner    │
        │  • MHRA             │  • Clinical Advisory│
        │  • Platform Ops     │  • Ethics Panel     │
        │  • AI Companion     │  • Mental Health    │
 P      │    Industry         │    Professionals    │
 O      │  • Funders          │  • DPO             │
 W      ├─────────────────────┼─────────────────────┤
 E      │                     │                     │
 R      │      MONITOR        │    KEEP INFORMED    │
        │                     │                     │
   Low  │                     │  • Users in         │
        │                     │    limerence        │
        │                     │  • LwL community    │
        │                     │  • Safeguarding     │
        │                     │  • Children's orgs  │
        │                     │  • Academics        │
        │                     │  • Dev team         │
        │                     │  • UX/Content       │
        └─────────────────────┴─────────────────────┘
```

| Stakeholder | Power | Interest | Quadrant | Engagement Strategy |
|-------------|-------|----------|----------|---------------------|
| Product Owner | HIGH | HIGH | Manage Closely | All decisions, vision holder |
| Clinical Advisory Board | HIGH | HIGH | Manage Closely | Protocol approval, safety gates |
| Ethics Review Panel | HIGH | HIGH | Manage Closely | Pre-launch sign-off, dual-use monitoring |
| Mental Health Professionals | HIGH | HIGH | Manage Closely | Co-design, clinical validation, referral pathway |
| DPO | HIGH | HIGH | Manage Closely | DPIA, consent architecture |
| ICO | HIGH | MEDIUM | Keep Satisfied | DPIA submission, transparency reporting |
| MHRA | HIGH | MEDIUM | Keep Satisfied | Classification assessment, regulatory pathway |
| Platform Operators | HIGH | MEDIUM | Keep Satisfied | Detection framework briefings |
| Funders | HIGH | MEDIUM | Keep Satisfied | Impact metrics, outcome reporting |
| AI Companion Industry | HIGH | LOW | Keep Satisfied | Published research, responsible disclosure framing |
| Users in Limerence | LOW | HIGH | Keep Informed | In-app psychoeducation, consent flows, feedback loops |
| Living with Limerence Community | MEDIUM | HIGH | Keep Informed | Community consultation, beta testing |
| Safeguarding Professionals | MEDIUM | HIGH | Keep Informed | Training materials, detection framework |
| Children's Safeguarding Orgs | MEDIUM | HIGH | Keep Informed | CSEA threat briefings, age-gating consultation |
| Academic Researchers | MEDIUM | HIGH | Keep Informed | Research collaboration, data sharing agreements |
| Law Enforcement | MEDIUM | MEDIUM | Keep Informed | Threat intelligence briefings |
| Development Team | MEDIUM | HIGH | Keep Informed | Sprint reviews, architecture decisions |
| UX / Content Design | MEDIUM | HIGH | Keep Informed | Design reviews, user research findings |

**Quadrant Interpretation:**

- **Manage Closely** (High Power, High Interest): Key decision-makers requiring active engagement
- **Keep Satisfied** (High Power, Low Interest): Influential stakeholders needing periodic updates
- **Keep Informed** (Low Power, High Interest): Engaged stakeholders needing regular communication
- **Monitor** (Low Power, Low Interest): Minimal engagement required

---

## Stakeholder Drivers Analysis

### SD-1: Users in Limerence — Relief from Involuntary Obsessive Attachment

**Stakeholder**: People currently experiencing limerence (primary user group)

**Driver Category**: CUSTOMER

**Driver Statement**: Users need immediate, accessible relief from the involuntary neurochemical state of limerence — intrusive thoughts occupying up to 85% of waking hours, dopamine-driven compulsive seeking behaviour, and acute distress during perceived separation from the limerent object [LM12-C1].

**Context & Background**:
Limerence produces its most acute distress at 3am, when therapists are unavailable and friends are asleep [LM35-C5]. Users are already on their phones engaging in digital rituals (checking social media, rereading messages) that reinforce the limerent cycle. Existing interventions — therapy, self-help books, willpower — are either unavailable at the point of crisis or insufficient to interrupt the neurochemistry. Insight alone does not stop limerence; behavioural intervention is required [LM12-C2].

**Driver Intensity**: CRITICAL

**Enablers**:

- 24/7 availability on mobile devices
- Clinically grounded CBT/ERP techniques delivered in conversational format
- Psychoeducation that creates cognitive distance ("this is dopamine, not destiny") [LM35-C6]
- Ritual tracking that makes progress visible

**Blockers**:

- Risk of forming attachment to the tool itself (the transfer problem)
- Stigma around admitting to limerence — many users do not know the term
- Tool could be perceived as a poor substitute for human connection
- Users in acute crystallisation phase may resist reality-testing

**Related Stakeholders**: Mental health professionals (SD-3), Living with Limerence community (SD-6)

---

### SD-2: Product Owner — Build the Defensive Application Before the Weapon

**Stakeholder**: Mark Craddock (Founder / Product Owner)

**Driver Category**: STRATEGIC

**Driver Statement**: Build and ship a clinically informed anti-attachment AI tool that demonstrates the defensive application of limerence knowledge before criminal actors weaponise the same knowledge at scale [LM35-C7].

**Context & Background**:
The romance scam industry generated over $1.3 billion in reported US losses in 2022, predating LLM availability [LM35-C8]. The exploitation pipeline documented in Part Three shows that AI-enabled limerence induction requires no novel technology — only the integration of published neuroscience with commodity infrastructure (LLMs, social media, crypto). The question is not whether it will happen but whether the defensive response will be ready [LM35-C9].

**Driver Intensity**: CRITICAL

**Enablers**:

- Published clinical framework (Wyant, 2021) provides treatment protocol [LM35-C4]
- Wardley mapping of exploitation landscape provides strategic clarity
- AI companion industry's existing products demonstrate the induction mechanism at scale
- Responsible disclosure framing provides ethical foundation for publication

**Blockers**:

- Dual-use concern: publishing the exploitation map makes the playbook visible
- Thin clinical evidence base (single case study) limits credibility
- Anti-dependency architecture limits engagement metrics that demonstrate traction
- Regulatory classification uncertainty (is this a medical device?)

**Related Stakeholders**: Ethics Review Panel (SD-5), Funders (SD-9), Regulators (SD-7, SD-8)

---

### SD-3: Mental Health Professionals — Credible Supplement, Not Replacement

**Stakeholder**: Therapists, counsellors, and psychiatrists

**Driver Category**: OPERATIONAL

**Driver Statement**: Mental health professionals need DeLimerence to be a credible, evidence-based supplement to therapy that does not undermine the therapeutic relationship, make clinical claims it cannot support, or position itself as a replacement for professional treatment.

**Context & Background**:
The clinical evidence base for limerence-specific treatment is extremely thin — Wyant (2021) is the only published case study [LM35-C4]. Most therapists are unfamiliar with limerence as a distinct clinical presentation and may interpret it as infatuation, attachment disorder, or obsessive-compulsive traits. A tool that educates professionals as well as users could expand the treatment landscape, but only if it earns professional trust.

**Driver Intensity**: HIGH

**Enablers**:

- Explicit positioning as supplement (graduated intervention after 10 sessions asks about therapist involvement) [LM35-C10]
- Transparent clinical framework based on published CBT/ERP protocols
- No warmth, no persona, no simulated emotional presence — clearly a tool, not a companion [LM35-C11]
- Outcome data that professionals can use to inform treatment

**Blockers**:

- Professional scepticism toward AI mental health tools
- Lack of clinical trials or RCT evidence
- Risk that users delay seeking professional help because the tool "feels like enough"
- Liability concerns if user harm occurs

**Related Stakeholders**: Users (SD-1), Clinical Advisory Board (SD-4), Academic Researchers (SD-10)

---

### SD-4: Clinical Advisory Board — Ensure Clinical Safety and Ethical Integrity

**Stakeholder**: Clinical Advisory Board (to be constituted)

**Driver Category**: COMPLIANCE

**Driver Statement**: Ensure that a tool interacting with psychologically vulnerable users during acute distress meets clinical safety standards, does not cause harm, and operates within an ethical framework appropriate to the sensitivity of the domain.

**Context & Background**:
DeLimerence operates at the intersection of AI, mental health, and vulnerable populations. Users in limerence have compromised executive function [LM12-C3], making informed consent more complex than for a general-purpose app. The anti-dependency architecture (session limits, cooldown periods, no persona) requires clinical validation to confirm these constraints help rather than frustrate [LM35-C3]. Phase-aware responses (crystallisation vs deterioration) require clinically sound decision logic [LM35-C12].

**Driver Intensity**: CRITICAL

**Enablers**:

- Structured clinical framework (ERP, ABCDE cognitive restructuring, behavioural activation)
- Anti-dependency architecture provides explicit safety constraints to evaluate
- Phase-aware response model provides clear intervention logic to review
- Published literature provides theoretical grounding

**Blockers**:

- No precedent for clinical governance of anti-attachment AI tools
- Difficulty constituting a board with limerence-specific expertise (very few specialists exist)
- Balancing clinical rigour with development speed
- Ethical complexity of dual-use knowledge

**Related Stakeholders**: Ethics Review Panel (SD-5), MHRA (SD-8), Mental Health Professionals (SD-3)

---

### SD-5: Ethics Review Panel — Manage the Dual-Use Problem Responsibly

**Stakeholder**: Ethics Review Panel (to be constituted)

**Driver Category**: RISK

**Driver Statement**: Ensure the project's publication of limerence exploitation mechanisms and the development of limerence-intervention technology is handled within a responsible disclosure framework that maximises defensive value and minimises enabling potential [LM35-C2].

**Context & Background**:
DeLimerence and the exploitation map exist on opposite sides of the same insight: limerence is a neurochemical mechanism that can be deliberately triggered, sustained, or interrupted [LM35-C13]. The same knowledge of dopamine reward circuits, intermittent reinforcement, and attachment profiling that makes the recovery tool possible also makes AI-enabled exploitation possible. The cybersecurity responsible disclosure analogy provides a framework, but the analogy is imperfect — in cybersecurity, disclosure comes with a patch; here, the "patch" is a prototype [LM35-C14].

**Driver Intensity**: HIGH

**Enablers**:

- Responsible disclosure precedent from cybersecurity community
- Mechanisms described are already in published scientific literature
- Existing romance scam industry demonstrates exploitation is already occurring
- Clear defensive framing in publication strategy

**Blockers**:

- No established ethical framework for dual-use AI mental health tools
- Media misinterpretation risk (framed as "how-to" rather than "defence")
- Difficulty measuring whether publication enables more harm than it prevents
- Reputational risk to project if exploitation techniques are attributed to the analysis

**Related Stakeholders**: Product Owner (SD-2), Academic Researchers (SD-10), Law Enforcement (SD-11)

---

### SD-6: Living with Limerence Community — Validation and Accessible Support

**Stakeholder**: Living with Limerence online community (founded by Dr L.)

**Driver Category**: CUSTOMER

**Driver Statement**: The established limerence community needs tools that validate their experience, align with the psychoeducation model they have built, and extend support to people who cannot access or afford therapy.

**Context & Background**:
The Living with Limerence blog and community has been the primary resource for people experiencing limerence, documenting extensively that securely attached adults in happy partnerships can be blindsided by limerence [LM12-C4]. The community has developed the concept of "purposeful living" as a recovery framework [LM35-C15]. DeLimerence's psychoeducation approach directly builds on this community's work.

**Driver Intensity**: HIGH

**Enablers**:

- Alignment with existing psychoeducation model (neuroscience-based explanation)
- Tool extends community's reach to point-of-crisis moments
- Ritual tracking maps to community's existing recovery practices
- Community provides built-in beta testing and feedback population

**Blockers**:

- Community may perceive the tool as commercialising their work
- Risk of fragmenting the support community
- Tool's anti-warmth approach may feel alienating to people used to peer support
- Community's approach is experience-based, not clinically validated — potential tension

**Related Stakeholders**: Users (SD-1), Mental Health Professionals (SD-3), Academic Researchers (SD-10)

---

### SD-7: ICO — Data Protection for Vulnerable Users

**Stakeholder**: Information Commissioner's Office

**Driver Category**: COMPLIANCE

**Driver Statement**: Ensure that personal data processing — particularly special category data (health data relating to mental health conditions) and potentially intimate content disclosures — is lawful, fair, transparent, and subject to appropriate safeguards under UK GDPR.

**Context & Background**:
DeLimerence will process highly sensitive data: users will disclose details of obsessive romantic attachment, specific limerent rituals, relationship information, and potentially distressing emotional states. Ritual tracking creates persistent records of mental health-adjacent behaviour over time. The user population has compromised executive function, raising questions about the quality of consent.

**Driver Intensity**: HIGH

**Enablers**:

- Data minimisation principle aligns with anti-dependency architecture (less data collected)
- Session limits and cooldown periods naturally reduce data volume
- No persona means no pseudo-relationship data to manage
- Clear legitimate interest / consent basis for clinical tool

**Blockers**:

- Special category data (health) requires Article 9 condition
- Compromised executive function complicates valid consent
- Ritual tracking creates longitudinal mental health records
- Cross-border data transfer issues if tool is available internationally

**Related Stakeholders**: DPO (internal), Clinical Advisory Board (SD-4), Users (SD-1)

---

### SD-8: MHRA — Medical Device Classification

**Stakeholder**: Medicines and Healthcare products Regulatory Agency

**Driver Category**: COMPLIANCE

**Driver Statement**: Determine whether DeLimerence meets the definition of a medical device under UK MDR 2002 (as amended) and, if so, ensure it follows the appropriate regulatory pathway before public deployment.

**Context & Background**:
Software that provides diagnosis, prevention, monitoring, prediction, prognosis, treatment, or alleviation of disease or a medical condition may be classified as a medical device. DeLimerence's CBT/ERP delivery, phase assessment (initiation, crystallisation, deterioration, resolution), and ritual tracking could be interpreted as treatment or monitoring of a mental health condition. The classification is consequential: medical device status would require CE/UKCA marking, clinical evidence, post-market surveillance, and quality management systems.

**Driver Intensity**: HIGH

**Enablers**:

- Positioning as "cognitive pattern interrupter" and psychoeducation tool (not treatment)
- No diagnostic claims — phase assessment is for response calibration, not clinical diagnosis
- Explicit "not a therapist" messaging throughout
- Anti-dependency architecture demonstrates tool is not designed for ongoing therapeutic relationship

**Blockers**:

- Regulatory boundary between "wellness tool" and "medical device" is ambiguous for AI mental health apps
- CBT/ERP delivery may cross the line into treatment
- Phase-aware responses could be interpreted as clinical triage
- Regulatory uncertainty creates delay and cost

**Related Stakeholders**: Clinical Advisory Board (SD-4), Product Owner (SD-2), Funders (SD-9)

---

### SD-9: Funders / Impact Investors — Demonstrable Social Impact with Sustainable Model

**Stakeholder**: Social impact investors, health tech funders, grant bodies

**Driver Category**: FINANCIAL

**Driver Statement**: Funders need evidence that DeLimerence produces measurable mental health outcomes, addresses a real and significant need, and can sustain itself financially — despite an anti-dependency architecture that deliberately limits engagement.

**Context & Background**:
The anti-dependency architecture creates an unusual funding challenge: session limits (20 exchanges), cooldown periods (8 hours), and the explicit goal of making the tool unnecessary all work against the engagement metrics that typically demonstrate product-market fit. The $1.3 billion romance scam figure and the companion AI industry's scale demonstrate market size, but DeLimerence deliberately inverts the revenue model that proves it [LM35-C8].

**Driver Intensity**: MEDIUM

**Enablers**:

- Measurable outcomes (ritual time reduction, session frequency decline over time)
- Social impact framing aligns with impact investing criteria
- Safeguarding / exploitation prevention angle opens government and charity funding
- "Tool designed to make itself unnecessary" is a compelling narrative for mission-driven funders

**Blockers**:

- Anti-dependency architecture limits recurring revenue and engagement metrics
- No clinical trial data yet
- Market size is difficult to quantify (limerence is underdiagnosed and under-recognised)
- Dual-use framing may concern risk-averse funders

**Related Stakeholders**: Product Owner (SD-2), Academic Researchers (SD-10), MHRA (SD-8)

---

### SD-10: Academic Researchers — Expand the Evidence Base

**Stakeholder**: Clinical psychology researchers, neuroscience departments, AI safety researchers

**Driver Category**: STRATEGIC

**Driver Statement**: Researchers need access to structured data on limerence presentation, intervention effectiveness, and AI-mediated CBT/ERP delivery to build the evidence base beyond the single published case study.

**Context & Background**:
The clinical evidence for limerence-specific treatment is limited to Wyant (2021) — a single case study of one patient [LM35-C4]. The Living with Limerence community has generated substantial experiential evidence but little peer-reviewed research. DeLimerence, at scale, could generate the first large-dataset evidence on limerence prevalence, phase distribution, ritual patterns, and intervention effectiveness — if data sharing is designed in from the start.

**Driver Intensity**: MEDIUM

**Enablers**:

- Structured ritual tracking creates quantitative outcome data
- Phase assessment generates prevalence data across the limerence lifecycle
- Anonymised, aggregated data could support multiple research programmes
- Tool design directly operationalises clinical protocols, enabling effectiveness measurement

**Blockers**:

- Data sharing requires ethics committee approval and user consent
- Data minimisation principle may conflict with research data richness
- Academic publication timelines are slow relative to product development
- Researchers may be sceptical of industry-generated data

**Related Stakeholders**: Clinical Advisory Board (SD-4), ICO (SD-7), Users (SD-1)

---

### SD-11: Law Enforcement & Safeguarding — Understand Limerence as an Attack Vector

**Stakeholder**: Police forces, National Crime Agency, local authority safeguarding teams

**Driver Category**: RISK

**Driver Statement**: Law enforcement and safeguarding professionals need to understand limerence-based exploitation as a distinct threat model — different from traditional romance fraud — and need detection and intervention frameworks that map to the AI-enabled exploitation pipeline [LM35-C16].

**Context & Background**:
The shift from external coercion (threats, blackmail) to internal coercion (neurochemical dependency) fundamentally changes the victim profile and investigation approach [LM35-C17]. Victims in a limerent state may continue to comply with exploitation even after the blackmail is revealed, because the limerent bond has not been broken. One AI operator can maintain thousands of simultaneous limerent relationships. Children and young people are neurologically more vulnerable [LM35-C18].

**Driver Intensity**: HIGH

**Enablers**:

- Wardley maps of exploitation pipeline provide strategic framework
- Detection of AI-driven intermittent reinforcement patterns is a tractable signal processing problem [LM35-C19]
- Existing Wardley mapping work on CSEA/sextortion provides foundation
- Cross-sector collaboration (platforms, law enforcement, safeguarding) is already established for CSEA

**Blockers**:

- Limerence is not widely understood in law enforcement
- No established training or recognition framework
- Victim behaviour (continued compliance) may be misinterpreted as consent
- AI-mediated grooming makes perpetrator identification extremely difficult

**Related Stakeholders**: Platform Operators (SD-12), Children's Safeguarding Orgs, Ethics Review Panel (SD-5)

---

### SD-12: Platform Operators — Detection Mechanisms for AI-Driven Exploitation

**Stakeholder**: Dating app operators, social media platforms

**Driver Category**: OPERATIONAL

**Driver Statement**: Platform operators need detection mechanisms to identify AI-driven intermittent reinforcement patterns in user interactions on their platforms, particularly where these patterns indicate weaponised limerence induction targeting their users [LM35-C19].

**Context & Background**:
The exploitation pipeline begins with contact through dating apps or social media [LM35-C20]. AI-driven personas optimised for specific attachment profiles are indistinguishable from genuine users through conventional moderation. The intermittent reinforcement pattern (warmth-distance-warmth-ambiguity) is the signature of weaponised limerence induction and is potentially detectable through interaction pattern analysis.

**Driver Intensity**: MEDIUM

**Enablers**:

- Platforms already invest in fraud and bot detection
- Intermittent reinforcement has a measurable temporal signature
- Regulatory pressure (Online Safety Act) creates compliance incentive
- Reputational interest in user protection

**Blockers**:

- Detection may generate false positives against normal human relationship behaviour
- Platform business models benefit from engagement (including attachment-driven engagement)
- Technical integration requires platform cooperation
- Privacy concerns about monitoring conversational patterns

**Related Stakeholders**: Law Enforcement (SD-11), ICO (SD-7), Users (SD-1)

---

## Driver-to-Goal Mapping

### Goal G-1: Deliver a Clinically Grounded Limerence Recovery Tool by Q4 2026

**Derived From Drivers**: SD-1, SD-2, SD-3, SD-4

**Goal Owner**: Product Owner (Mark Craddock)

**Goal Statement**: Launch a public beta of DeLimerence that implements the full anti-dependency architecture (session limits, cooldown periods, no persona, phase-aware responses, ritual tracking) with clinical advisory board sign-off, by Q4 2026.

**Why This Matters**: Users need relief now — limerence distress is acute and existing tools are insufficient. The defensive application must exist before AI-enabled exploitation scales further. Every month of delay is a month where the weapon exists without the antidote.

**Success Metrics**:

- **Primary Metric**: Public beta launch with all 9 anti-dependency features operational
- **Secondary Metrics**:
  - Clinical advisory board sign-off on intervention protocols
  - Ethics review panel approval of dual-use risk management
  - Phase assessment accuracy validated against clinical judgement (target: > 80% agreement)

**Baseline**: No tool exists

**Target**: Operational public beta with clinical governance

**Measurement Method**: Feature completion tracking, clinical review minutes, ethics panel reports

**Dependencies**:

- Constitution of clinical advisory board with limerence/OCD expertise
- Regulatory pathway clarity from MHRA (wellness tool vs medical device)
- LLM foundation model selection and safety testing

**Risks to Achievement**:

- Medical device classification triggers extended regulatory pathway (12-18 month delay)
- Unable to recruit clinical advisors with limerence-specific expertise
- Phase-aware response logic fails safety testing (harmful responses in edge cases)

---

### Goal G-2: Demonstrate Measurable Reduction in Limerent Rituals Within 90 Days of Use

**Derived From Drivers**: SD-1, SD-3, SD-9, SD-10

**Goal Owner**: Clinical Advisory Board

**Goal Statement**: Show that users who complete at least 10 DeLimerence sessions over 90 days reduce self-reported time spent on limerent rituals by 50% or more, benchmarked against Wyant (2021) where ritual time dropped from 8+ hours to 10 minutes over 9 months [LM35-C4].

**Why This Matters**: Without measurable outcomes, the tool has no clinical credibility, no research value, and no basis for funding. The Wyant case study sets the only published benchmark — DeLimerence must at minimum match this trajectory.

**Success Metrics**:

- **Primary Metric**: Median reduction in self-reported daily ritual time (hours)
- **Secondary Metrics**:
  - Session frequency decline over time (tool making itself unnecessary)
  - User-reported distress level (validated scale, e.g., adapted Y-BOCS)
  - Phase progression (users moving from crystallisation toward resolution)

**Baseline**: User self-report at intake (estimated 2-8 hours daily ritual time based on literature)

**Target**: 50% reduction in median daily ritual time within 90 days

**Measurement Method**: In-app ritual tracking, periodic self-assessment prompts, anonymised aggregate analysis

**Dependencies**:

- Ritual tracking feature operational and validated
- Sufficient user volume for statistical significance (minimum n=100)
- Ethics-approved data collection and analysis protocol

**Risks to Achievement**:

- Self-report bias (users may under- or over-report)
- High dropout rate before 10 sessions (limerence may resolve or user disengages)
- Anti-dependency architecture limits session frequency, potentially slowing progress

---

### Goal G-3: Establish Regulatory Pathway Within 6 Months of Project Start

**Derived From Drivers**: SD-7, SD-8, SD-4

**Goal Owner**: Data Protection Officer / Product Owner

**Goal Statement**: Obtain written guidance from MHRA on device classification and complete a DPIA submission to ICO by October 2026, establishing the regulatory basis for public deployment.

**Why This Matters**: Regulatory uncertainty is the single biggest risk to the project timeline. The boundary between "wellness tool" and "medical device" is ambiguous for AI mental health apps. Resolving this early prevents wasted development effort on the wrong regulatory pathway.

**Success Metrics**:

- **Primary Metric**: Written MHRA classification determination received
- **Secondary Metrics**:
  - DPIA completed and submitted to ICO
  - Consent architecture designed and validated for compromised executive function
  - Article 9 lawful basis for special category data processing confirmed

**Baseline**: No regulatory engagement

**Target**: Classification determination and DPIA submission within 6 months

**Measurement Method**: Regulatory correspondence tracking, DPIA completion milestones

**Dependencies**:

- Clinical advisory board constituted (needed for MHRA engagement)
- Product feature specification finalised (MHRA needs to assess specific functionality)
- Legal counsel with medical device and data protection expertise

**Risks to Achievement**:

- MHRA classifies as medical device, triggering CE/UKCA pathway (12-18 month additional timeline)
- ICO raises concerns about consent validity for users with compromised executive function
- Regulatory guidance is ambiguous or delayed

---

### Goal G-4: Prevent User Attachment to the Tool — Zero Limerence Transfer Cases

**Derived From Drivers**: SD-1, SD-4, SD-5, SD-3

**Goal Owner**: Clinical Advisory Board

**Goal Statement**: Demonstrate through user research and outcome tracking that the anti-dependency architecture effectively prevents users from developing attachment to DeLimerence itself, with zero reported cases of limerence transfer to the tool within the first year of operation.

**Why This Matters**: This is the existential risk for the product. If users become limerent toward the recovery tool, DeLimerence becomes another companion AI — the very thing it was designed to counteract. The anti-dependency architecture (session limits, cooldown, no persona, anti-warmth prompting, action commitment gates) exists specifically to prevent this [LM35-C3].

**Success Metrics**:

- **Primary Metric**: Zero reported cases of limerence transfer to the tool
- **Secondary Metrics**:
  - Session frequency per user declining over time (not escalating)
  - User sentiment toward tool remains instrumental ("useful") not relational ("I need it")
  - Cooldown period compliance rate (users not attempting to circumvent the 8-hour gap)

**Baseline**: No data (novel design pattern)

**Target**: Zero transfer cases; declining session frequency curve; > 90% cooldown compliance

**Measurement Method**: User surveys, usage pattern analysis, qualitative exit interviews, clinical advisory board case review

**Dependencies**:

- Anti-dependency architecture fully implemented and enforced at infrastructure level
- Monitoring instruments designed and validated
- Clinical advisory board defines criteria for "attachment to tool" identification

**Risks to Achievement**:

- Anti-dependency measures are insufficient — some users develop attachment despite constraints
- Users circumvent cooldown periods via multiple accounts
- Qualitative signals of attachment are missed by automated monitoring

---

### Goal G-5: Establish Limerence as a Recognised Attack Vector in Safeguarding Practice

**Derived From Drivers**: SD-2, SD-11, SD-12, SD-5

**Goal Owner**: Product Owner

**Goal Statement**: Publish the exploitation analysis and Wardley maps, brief at least 3 safeguarding organisations and 1 law enforcement body, and secure adoption of the limerence threat model in at least one formal safeguarding training programme by end of 2027.

**Why This Matters**: The defensive value of the DeLimerence project extends beyond the tool itself. If safeguarding professionals and law enforcement do not understand limerence as an attack vector, AI-enabled exploitation will scale undetected. Awareness is the first layer of defence [LM35-C16].

**Success Metrics**:

- **Primary Metric**: Limerence threat model adopted in at least 1 safeguarding training programme
- **Secondary Metrics**:
  - Exploitation analysis published and peer-reviewed
  - Briefings delivered to 3+ safeguarding organisations
  - At least 1 law enforcement body acknowledges the threat model
  - Platform operators engaged on detection mechanisms

**Baseline**: Limerence is not recognised as an attack vector in any safeguarding framework

**Target**: Formal recognition in at least 1 training programme by end 2027

**Measurement Method**: Publication citations, briefing attendance records, training programme curriculum review

**Dependencies**:

- Ethics review panel approval of publication strategy
- Responsible disclosure framework agreed
- Credibility established through clinical advisory board endorsement

**Risks to Achievement**:

- Publication is misinterpreted as enabling rather than defensive
- Safeguarding community does not take limerence threat seriously
- AI companion industry pushback undermines credibility
- Media coverage focuses on exploitation rather than defence

---

## Goal-to-Outcome Mapping

### Outcome O-1: Measurable Recovery — Users Regain Cognitive Control

**Supported Goals**: G-1, G-2, G-4

**Outcome Statement**: Users who engage with DeLimerence experience measurable reduction in limerent symptoms (ritual time, intrusive thought frequency, distress levels) and regain executive function, as demonstrated by declining tool usage and increasing real-world activity.

**Measurement Details**:

- **KPI**: Median daily ritual time (hours)
- **Current Value**: 2-8 hours (estimated from literature and community reports)
- **Target Value**: < 30 minutes within 90 days; < 10 minutes within 6 months
- **Measurement Frequency**: Weekly (via in-app ritual tracking)
- **Data Source**: User self-report through ritual tracking feature
- **Report Owner**: Clinical Advisory Board

**Business Value**:

- **Financial Impact**: Demonstrates product-market fit for funders; enables outcome-based pricing models
- **Strategic Impact**: First quantitative evidence base for limerence intervention at scale
- **Operational Impact**: Validates CBT/ERP protocol in conversational AI format
- **Customer Impact**: Direct improvement in quality of life for users

**Timeline**:

- **Phase 1 (Months 1-3)**: Beta users onboarded, baseline ritual time established, initial trend data
- **Phase 2 (Months 4-6)**: 50% reduction target assessed, phase progression tracked
- **Phase 3 (Months 7-12)**: 90% reduction target for engaged users, dropout analysis, outcome report published
- **Sustainment (Year 2+)**: Longitudinal follow-up, relapse rate measurement

**Stakeholder Benefits**:

- **Users**: Relief from acute distress, restored daily functioning
- **Mental Health Professionals**: Evidence-based referral option, treatment data
- **Funders**: Measurable social impact, outcome data for reporting
- **Academic Researchers**: First large-scale limerence intervention dataset

**Leading Indicators** (early signals of success):

- Users engaging with ritual tracking feature (adoption rate > 60%)
- Self-reported distress declining within first 5 sessions
- Users completing action commitment gates with real-world activities

**Lagging Indicators** (final proof of success):

- 90-day ritual time reduction target met
- Session frequency declining (tool becoming unnecessary)
- User exits with positive outcome (resolution phase reached)

---

### Outcome O-2: Anti-Dependency Validated — Tool Does Not Create New Harm

**Supported Goals**: G-4, G-1

**Outcome Statement**: The anti-dependency architecture demonstrably prevents user attachment to the tool, as evidenced by declining usage curves, zero limerence transfer cases, and clinical advisory board sign-off that the tool operates within safe parameters.

**Measurement Details**:

- **KPI**: Limerence transfer incident count
- **Current Value**: N/A (novel design)
- **Target Value**: Zero
- **Measurement Frequency**: Monthly (clinical review), continuous (automated monitoring)
- **Data Source**: Usage pattern analysis, user surveys, clinical case review
- **Report Owner**: Clinical Advisory Board

**Business Value**:

- **Financial Impact**: Eliminates liability risk; strengthens regulatory position
- **Strategic Impact**: Establishes a replicable design pattern for anti-dependency AI
- **Operational Impact**: Validates architectural constraints as effective safety controls
- **Customer Impact**: Users are protected from iatrogenic harm

**Timeline**:

- **Phase 1 (Months 1-3)**: Monitoring instruments deployed, baseline usage patterns established
- **Phase 2 (Months 4-6)**: First cohort analysis — usage curves, sentiment analysis, cooldown compliance
- **Phase 3 (Months 7-12)**: Full-year assessment, clinical advisory board sign-off
- **Sustainment (Year 2+)**: Continuous monitoring, annual safety review

**Stakeholder Benefits**:

- **Users**: Protected from developing a new dependency
- **Clinical Advisory Board**: Evidence that safety constraints work
- **Regulators**: Demonstrable harm prevention
- **AI Safety Researchers**: Novel anti-dependency design pattern for the field

**Leading Indicators**:

- Cooldown compliance rate > 90%
- No escalation in session frequency per user over time
- User language remains instrumental ("the tool helped me") not relational ("I need to talk to it")

**Lagging Indicators**:

- Zero transfer cases at 12-month review
- Declining average session frequency across the user base
- Clinical advisory board annual safety sign-off achieved

---

### Outcome O-3: Regulatory Clarity — Lawful Deployment Basis Established

**Supported Goals**: G-3

**Outcome Statement**: DeLimerence has a clear, documented regulatory pathway — MHRA classification determination, ICO-approved DPIA, validated consent architecture — enabling public deployment without legal or compliance risk.

**Measurement Details**:

- **KPI**: Regulatory milestones completed (out of 4: MHRA determination, DPIA submission, consent validation, Article 9 basis)
- **Current Value**: 0 of 4
- **Target Value**: 4 of 4
- **Measurement Frequency**: Monthly milestone tracking
- **Data Source**: Regulatory correspondence, DPIA documentation, legal opinions
- **Report Owner**: DPO / Product Owner

**Business Value**:

- **Financial Impact**: Avoids fines (ICO), avoids forced withdrawal (MHRA)
- **Strategic Impact**: Sets precedent for anti-dependency AI regulatory treatment
- **Operational Impact**: Unblocks public deployment
- **Customer Impact**: Users have confidence in data protection and safety

**Timeline**:

- **Phase 1 (Months 1-3)**: MHRA pre-submission meeting, DPIA drafting commenced
- **Phase 2 (Months 4-6)**: MHRA determination received, DPIA submitted
- **Phase 3 (Months 7-12)**: Consent architecture validated, full compliance achieved
- **Sustainment (Year 2+)**: Annual DPIA review, regulatory relationship maintained

**Stakeholder Benefits**:

- **ICO**: Demonstrable compliance from a sensitive-data AI tool
- **MHRA**: Clarity on AI mental health tool classification
- **Users**: Confidence that data is protected
- **Funders**: Reduced regulatory risk to investment

**Leading Indicators**:

- MHRA pre-submission meeting scheduled
- DPIA draft completed and internally reviewed
- Legal opinion on Article 9 basis obtained

**Lagging Indicators**:

- Written MHRA classification received
- DPIA accepted by ICO
- First user onboarded under validated consent framework

---

### Outcome O-4: Threat Awareness — Limerence Recognised as Exploitation Vector

**Supported Goals**: G-5

**Outcome Statement**: Safeguarding professionals, law enforcement, and platform operators recognise AI-enabled limerence induction as a distinct threat model, with at least one formal training programme incorporating the exploitation analysis.

**Measurement Details**:

- **KPI**: Number of organisations formally adopting the threat model
- **Current Value**: 0
- **Target Value**: 4+ (1 training programme, 1 law enforcement body, 2 safeguarding organisations)
- **Measurement Frequency**: Quarterly
- **Data Source**: Briefing records, training programme curricula, formal acknowledgements
- **Report Owner**: Product Owner

**Business Value**:

- **Financial Impact**: Opens government/charity funding for safeguarding applications
- **Strategic Impact**: Positions DeLimerence as the authoritative voice on limerence exploitation
- **Operational Impact**: Creates demand for detection tools and intervention frameworks
- **Customer Impact**: Potential victims are better protected by informed professionals

**Timeline**:

- **Phase 1 (Months 1-3)**: Exploitation analysis published, initial briefing to 1 safeguarding body
- **Phase 2 (Months 4-6)**: 3+ briefings delivered, feedback incorporated
- **Phase 3 (Months 7-12)**: Training programme pilot, law enforcement engagement
- **Sustainment (Year 2+)**: Ongoing training delivery, updated threat assessments

**Stakeholder Benefits**:

- **Law Enforcement**: New investigation framework for AI-mediated exploitation
- **Safeguarding Professionals**: Updated training for AI-era threats
- **Platform Operators**: Detection signatures for weaponised limerence patterns
- **Children's Safeguarding Orgs**: CSEA prevention framework for AI companions

**Leading Indicators**:

- Publication engagement metrics (reads, shares, citations)
- Briefing invitations received
- Media coverage with defensive (not enabling) framing

**Lagging Indicators**:

- Formal training programme adoption
- Law enforcement acknowledgement in threat assessment
- Platform operator pilot of detection mechanism

---

## Complete Traceability Matrix

### Stakeholder → Driver → Goal → Outcome

| Stakeholder | Driver ID | Driver Summary | Goal ID | Goal Summary | Outcome ID | Outcome Summary |
|-------------|-----------|----------------|---------|--------------|------------|-----------------|
| Users in Limerence | SD-1 | Relief from obsessive attachment | G-1 | Deliver recovery tool by Q4 2026 | O-1 | Measurable recovery |
| Users in Limerence | SD-1 | Relief from obsessive attachment | G-2 | 50% ritual reduction in 90 days | O-1 | Measurable recovery |
| Users in Limerence | SD-1 | Relief from obsessive attachment | G-4 | Zero limerence transfer cases | O-2 | Anti-dependency validated |
| Product Owner | SD-2 | Build defence before weapon scales | G-1 | Deliver recovery tool by Q4 2026 | O-1 | Measurable recovery |
| Product Owner | SD-2 | Build defence before weapon scales | G-5 | Establish limerence as attack vector | O-4 | Threat awareness |
| Mental Health Professionals | SD-3 | Credible supplement, not replacement | G-2 | 50% ritual reduction in 90 days | O-1 | Measurable recovery |
| Mental Health Professionals | SD-3 | Credible supplement, not replacement | G-4 | Zero limerence transfer cases | O-2 | Anti-dependency validated |
| Clinical Advisory Board | SD-4 | Clinical safety and ethical integrity | G-1 | Deliver recovery tool by Q4 2026 | O-1 | Measurable recovery |
| Clinical Advisory Board | SD-4 | Clinical safety and ethical integrity | G-4 | Zero limerence transfer cases | O-2 | Anti-dependency validated |
| Clinical Advisory Board | SD-4 | Clinical safety and ethical integrity | G-3 | Regulatory pathway by Oct 2026 | O-3 | Regulatory clarity |
| Ethics Review Panel | SD-5 | Manage dual-use responsibly | G-5 | Establish limerence as attack vector | O-4 | Threat awareness |
| Ethics Review Panel | SD-5 | Manage dual-use responsibly | G-4 | Zero limerence transfer cases | O-2 | Anti-dependency validated |
| LwL Community | SD-6 | Validation and accessible support | G-2 | 50% ritual reduction in 90 days | O-1 | Measurable recovery |
| ICO | SD-7 | Data protection for vulnerable users | G-3 | Regulatory pathway by Oct 2026 | O-3 | Regulatory clarity |
| MHRA | SD-8 | Medical device classification | G-3 | Regulatory pathway by Oct 2026 | O-3 | Regulatory clarity |
| Funders | SD-9 | Demonstrable impact, sustainable model | G-2 | 50% ritual reduction in 90 days | O-1 | Measurable recovery |
| Academic Researchers | SD-10 | Expand the evidence base | G-2 | 50% ritual reduction in 90 days | O-1 | Measurable recovery |
| Law Enforcement | SD-11 | Limerence as attack vector | G-5 | Establish limerence as attack vector | O-4 | Threat awareness |
| Platform Operators | SD-12 | Detection mechanisms | G-5 | Establish limerence as attack vector | O-4 | Threat awareness |

### Conflict Analysis

**Competing Drivers**:

- **Conflict 1**: **Users (SD-1)** need 24/7 availability and low friction access, but **Clinical Advisory Board (SD-4)** and **MHRA (SD-8)** require safety constraints and potentially medical device compliance that slow deployment and add barriers.
  - **Resolution Strategy**: Phased launch — start with psychoeducation-only mode (lower regulatory risk), add CBT/ERP intervention features once classification is resolved. Session limits and cooldown periods serve both safety and regulatory purposes.

- **Conflict 2**: **Product Owner (SD-2)** wants to publish the exploitation analysis for defensive value, but **Ethics Review Panel (SD-5)** is concerned about enabling potential.
  - **Resolution Strategy**: Responsible disclosure model — publish with simultaneous release of DeLimerence prototype (the "patch"), explicit defensive framing, and pre-publication briefing to safeguarding organisations so the defensive community is prepared.

- **Conflict 3**: **Funders (SD-9)** need engagement metrics demonstrating traction, but **the anti-dependency architecture** deliberately suppresses engagement (session limits, cooldown, goal of making tool unnecessary).
  - **Resolution Strategy**: Reframe success metrics — measure outcome velocity (how quickly users recover), not engagement depth (how long they stay). Declining usage is the success metric, not a failure signal. Target impact investors and grant bodies rather than growth-stage VCs.

- **Conflict 4**: **Academic Researchers (SD-10)** want rich longitudinal data, but **ICO (SD-7)** requires data minimisation and **Users (SD-1)** have compromised consent capacity.
  - **Resolution Strategy**: Design opt-in research participation as a separate consent flow, with enhanced informed consent process (e.g., 48-hour reflection period before research consent activates). Aggregate and anonymise by default; individual-level data only with explicit research consent.

**Synergies**:

- **Synergy 1**: SD-1 (user relief) and SD-4 (clinical safety) both benefit from the anti-dependency architecture — it protects users and satisfies clinical governance simultaneously
- **Synergy 2**: SD-2 (build defence) and SD-11 (law enforcement awareness) align perfectly — the exploitation analysis serves both product rationale and safeguarding intelligence
- **Synergy 3**: SD-9 (funder metrics) and SD-10 (research data) both need measurable outcomes from the same ritual tracking and phase assessment features
- **Synergy 4**: SD-3 (therapist credibility) and SD-8 (MHRA clarity) both benefit from explicit "not a therapist, not a replacement" positioning

---

## Communication & Engagement Plan

### Users in Limerence

**Primary Message**: DeLimerence is a tool — not a companion, not a therapist — that uses neuroscience to help you understand and interrupt the limerence cycle. It is designed to make itself unnecessary.

**Key Talking Points**:

- What you are experiencing has a name, a neurochemical mechanism, and a recovery path
- This tool meets you at 3am when the spiralling is worst, but its job is to get you back into your real life
- It tracks your progress so you can see the numbers change — limerence is not permanent

**Communication Frequency**: In-app only (no push notifications, no re-engagement campaigns — anti-dependency principle)

**Preferred Channel**: In-app psychoeducation, onboarding flow, consent screens

**Success Story**: "I used DeLimerence for 6 weeks. I went from checking his Instagram 40 times a day to twice. The tool helped me see the pattern. I don't need it anymore."

---

### Mental Health Professionals

**Primary Message**: DeLimerence is a clinically informed supplement that operationalises CBT/ERP for limerence — the same approach validated in Wyant (2021). It explicitly directs users toward professional therapy and positions itself as a between-sessions support tool.

**Key Talking Points**:

- Built on published CBT/ERP protocols, not proprietary wellness claims
- Anti-dependency architecture prevents therapeutic relationship formation with the tool
- Generates outcome data (ritual time, phase progression) that can inform professional treatment
- After 10 sessions, the tool actively asks users whether they are working with a therapist

**Communication Frequency**: Quarterly (research updates, outcome reports)

**Preferred Channel**: Professional publications, conference presentations, clinical network briefings

**Success Story**: "My client used DeLimerence between our sessions. The ritual tracking gave us both data to work with, and the psychoeducation meant she arrived already understanding the neuroscience."

---

### Safeguarding Professionals & Law Enforcement

**Primary Message**: Limerence is an attack vector — not a curiosity. AI-enabled exploitation uses internal coercion (neurochemical dependency) rather than external coercion (threats), making victims harder to identify and the perpetrator invisible.

**Key Talking Points**:

- The exploitation pipeline has 6 stages; AI industrialises the grooming component
- Victims may continue complying even after the exploit is revealed (limerence bond persists)
- Children and young people are neurologically more vulnerable
- Detection of intermittent reinforcement patterns on platforms is tractable

**Communication Frequency**: Bi-annual (threat briefings), as-needed (incident response)

**Preferred Channel**: Briefing documents, training workshops, conference presentations

**Success Story**: "After the limerence threat briefing, our team identified a pattern in three cases we'd filed as standard romance fraud. The victim behaviour made no sense under the old model. It makes sense now."

---

### Regulators (ICO, MHRA)

**Primary Message**: DeLimerence is designed with data protection and clinical safety as architectural constraints, not afterthoughts. We are seeking early engagement to establish the correct regulatory pathway.

**Key Talking Points**:

- Anti-dependency architecture naturally minimises data collection
- Session limits and cooldown periods reduce data volume and processing intensity
- Consent architecture is designed for users with potentially compromised executive function
- Seeking MHRA classification guidance proactively, before public deployment

**Communication Frequency**: As-needed (regulatory submissions, pre-submission meetings)

**Preferred Channel**: Formal regulatory correspondence, pre-submission meetings

**Success Story**: "DeLimerence set a new standard for how AI mental health tools engage with regulators — early, transparently, and with safety built into the architecture rather than bolted on."

---

## Change Impact Assessment

### Impact on Stakeholders

| Stakeholder | Current State | Future State | Change Magnitude | Resistance Risk | Mitigation Strategy |
|-------------|---------------|--------------|------------------|-----------------|---------------------|
| Users in Limerence | No dedicated tool; rely on willpower, books, community forums, or therapy (if available) | Access to 24/7 clinically grounded intervention with ritual tracking and psychoeducation | HIGH | LOW | Clear onboarding explaining what the tool is and is not |
| Mental Health Professionals | Limerence rarely recognised; no specific treatment protocol widely adopted | Referral pathway to supplement therapy; outcome data available | MEDIUM | MEDIUM | Positioning as supplement; clinical advisory board endorsement |
| Safeguarding Professionals | Limerence not recognised as attack vector; standard romance fraud training | New threat model requiring updated training and detection frameworks | HIGH | MEDIUM | Briefings framed as evolution of existing CSEA/sextortion understanding |
| Law Enforcement | AI-mediated grooming understood conceptually but limerence mechanism not mapped | Specific exploitation pipeline with detection signatures | HIGH | HIGH | Ground analysis in existing Wardley mapping work they may already know |
| Platform Operators | Bot/fraud detection focused on account-level signals | Behavioural pattern detection (intermittent reinforcement signatures) | MEDIUM | MEDIUM | Frame as extension of existing trust & safety investment |
| Regulators | No precedent for anti-dependency AI mental health tools | New regulatory category requiring classification determination | MEDIUM | LOW | Proactive engagement; transparent design documentation |

### Change Readiness

**Champions** (Enthusiastic supporters):

- **Living with Limerence community** — Have been advocating for limerence recognition for years; tool validates their experience
- **AI safety researchers** — Anti-dependency architecture is a novel, publishable design pattern
- **Safeguarding charities** — Constantly seeking updated threat intelligence for AI-era harms

**Fence-sitters** (Neutral, need convincing):

- **Mental health professionals** — Need clinical trial evidence, not just case study extrapolation; will engage once outcome data is available
- **Platform operators** — Interested in user protection but wary of detection mechanism complexity and false positives
- **Funders** — Compelling narrative but unusual metrics model; need to see early outcome data

**Resisters** (Opposed or skeptical):

- **AI companion industry** — Analysis directly critiques their business model; likely to challenge framing publicly. Strategy: focus on evidence and clinical data, not industry adversarialism
- **Some clinicians** — May view AI-delivered CBT as professionally inappropriate regardless of safeguards. Strategy: position as psychoeducation + behaviour tracking rather than therapy delivery
- **Risk-averse legal advisors** — May recommend against publication of exploitation analysis. Strategy: responsible disclosure framework with ethics panel sign-off

---

## Risk Register (Stakeholder-Related)

### Risk R-1: Limerence Transfer to the Tool

**Related Stakeholders**: Users (SD-1), Clinical Advisory Board (SD-4), Ethics Panel (SD-5)

**Risk Description**: Despite the anti-dependency architecture, some users develop attachment to or dependency on DeLimerence itself, replicating the limerence pattern with the tool as limerent object.

**Impact on Goals**: G-4 (zero transfer cases), G-1 (clinical credibility), G-2 (outcome validity)

**Probability**: MEDIUM

**Impact**: HIGH

**Mitigation Strategy**: Nine architectural constraints (session limits, cooldown, no persona, anti-warmth prompt, action gates, graduated intervention, phase-aware responses, ritual tracking, psychoeducation); continuous monitoring for attachment signals; clinical advisory board quarterly review of usage patterns

**Contingency Plan**: If transfer case identified: immediate clinical advisory board review, potential temporary tool suspension for affected user with warm handoff to professional support, architectural review to strengthen constraints

---

### Risk R-2: MHRA Medical Device Classification

**Related Stakeholders**: MHRA (SD-8), Product Owner (SD-2), Funders (SD-9)

**Risk Description**: MHRA classifies DeLimerence as a medical device, triggering CE/UKCA marking requirements, clinical evidence obligations, and quality management system implementation — adding 12-18 months and significant cost to the regulatory pathway.

**Impact on Goals**: G-1 (launch timeline), G-3 (regulatory pathway), G-5 (threat awareness delayed if tool is not available)

**Probability**: MEDIUM

**Impact**: HIGH

**Mitigation Strategy**: Early MHRA pre-submission meeting to get informal guidance; design psychoeducation-only mode that clearly falls below device threshold as initial launch; position CBT/ERP features as "self-help techniques" rather than "treatment"

**Contingency Plan**: If classified as device: pivot to psychoeducation + ritual tracking only (non-device scope) for initial launch; pursue device pathway for CBT/ERP features as Phase 2; seek regulatory sandbox if available

---

### Risk R-3: Publication Backlash on Exploitation Analysis

**Related Stakeholders**: Ethics Panel (SD-5), Product Owner (SD-2), Law Enforcement (SD-11)

**Risk Description**: Publication of the limerence exploitation pipeline and Wardley map is framed by media or critics as enabling criminal activity rather than defensive analysis, damaging project credibility and stakeholder trust.

**Impact on Goals**: G-5 (threat awareness), G-1 (overall credibility), G-9 (funder confidence)

**Probability**: MEDIUM

**Impact**: MEDIUM

**Mitigation Strategy**: Pre-publication briefing to safeguarding organisations; simultaneous release of defensive tool (DeLimerence) alongside exploitation analysis; explicit responsible disclosure framing; ethics panel sign-off on publication strategy; embargo with selected journalists for accurate first-coverage

**Contingency Plan**: If backlash occurs: prepared response emphasising that all mechanisms are already in published literature; redirect attention to defensive application; engage credible third-party voices (safeguarding professionals, academics) to validate the framing

---

### Risk R-4: Insufficient Clinical Expertise Available

**Related Stakeholders**: Clinical Advisory Board (SD-4), Mental Health Professionals (SD-3), Academic Researchers (SD-10)

**Risk Description**: Unable to constitute a clinical advisory board with limerence-specific expertise, as very few clinicians specialise in limerence and the condition is not formally recognised in DSM-5 or ICD-11.

**Impact on Goals**: G-1 (launch requires clinical sign-off), G-2 (outcome validation), G-3 (MHRA engagement needs clinical backing)

**Probability**: HIGH

**Impact**: MEDIUM

**Mitigation Strategy**: Recruit from adjacent specialisms — OCD specialists (same neurochemical and treatment model), addiction psychiatrists (same reward circuit involvement), attachment researchers; engage Dr L. (Living with Limerence) as experiential advisor; engage Wyant as published clinical voice

**Contingency Plan**: If cannot recruit formal board: constitute informal advisory group with broader expertise; commission independent clinical review of protocols; partner with university department for academic credibility

---

### Risk R-5: User Harm from Phase Misassessment

**Related Stakeholders**: Users (SD-1), Clinical Advisory Board (SD-4), MHRA (SD-8)

**Risk Description**: Phase-aware response system incorrectly assesses a user's limerence phase (e.g., assessing crystallisation when the user is in deterioration) and delivers inappropriate intervention (aggressive reality-testing when grief support is needed), causing distress or harm.

**Impact on Goals**: G-1 (safety), G-2 (outcomes), G-4 (trust)

**Probability**: MEDIUM

**Impact**: HIGH

**Mitigation Strategy**: Phase assessment validated against clinical judgement before deployment (target > 80% agreement); conservative default (default to least harmful response category when uncertain); user override capability ("this doesn't feel right" triggers reassessment); clinical advisory board review of edge cases

**Contingency Plan**: If harm occurs: immediate incident response protocol, affected user connected to professional support, clinical advisory board emergency review, phase assessment model retrained or simplified

---

## Governance & Decision Rights

### Decision Authority Matrix (RACI)

| Decision Type | Responsible | Accountable | Consulted | Informed |
|---------------|-------------|-------------|-----------|----------|
| Product vision and strategy | Product Owner | Product Owner | Clinical Advisory Board, Ethics Panel | All stakeholders |
| Clinical protocol design | Clinical Advisory Board | Product Owner | Mental Health Professionals, Academic Researchers | Users, Funders |
| Anti-dependency architecture | Development Team | Product Owner | Clinical Advisory Board, UX/Content | Ethics Panel, Funders |
| Phase assessment logic | Development Team | Clinical Advisory Board | Mental Health Professionals | Users, MHRA |
| Data protection (DPIA, consent) | DPO | Product Owner | ICO (consulted via submissions), Legal | Clinical Advisory Board |
| Regulatory pathway (MHRA) | Product Owner | Product Owner | Clinical Advisory Board, Legal | Funders, Dev Team |
| Exploitation analysis publication | Product Owner | Ethics Review Panel | Law Enforcement, Safeguarding Orgs | Academic Researchers, Media |
| Go/No-go for public beta | Product Owner | Clinical Advisory Board | Ethics Panel, DPO, MHRA | All stakeholders |
| Funding and financial model | Product Owner | Product Owner | Funders | All stakeholders |
| Incident response (user harm) | Clinical Advisory Board | Product Owner | DPO, Legal | Regulators, Ethics Panel |

### Escalation Path

1. **Level 1**: Development Team / UX (day-to-day implementation decisions)
2. **Level 2**: Product Owner (scope, timeline, feature prioritisation, stakeholder conflicts)
3. **Level 3**: Clinical Advisory Board (clinical safety decisions, phase assessment disputes, harm incidents)
4. **Level 4**: Ethics Review Panel (dual-use decisions, publication strategy, fundamental design challenges)

---

## Validation & Sign-off

### Stakeholder Review

| Stakeholder | Review Date | Comments | Status |
|-------------|-------------|----------|--------|
| Product Owner | PENDING | Initial review | PENDING |
| Clinical Advisory Board | PENDING | Awaiting constitution | PENDING |
| Ethics Review Panel | PENDING | Awaiting constitution | PENDING |

### Document Approval

| Role | Name | Signature | Date |
|------|------|-----------|------|
| Product Owner | Mark Craddock | | |
| Clinical Lead | | | |
| Ethics Chair | | | |

---

## Appendices

### Appendix A: Source Document Analysis

The stakeholder analysis was derived from two source documents:

1. **The Limerence Machine: Parts 1-2** — Establishes the neuroscience of limerence and the AI companion industry's role as limerence engines. Provides the clinical and neurochemical foundation for understanding user needs and the threat landscape.

2. **The Limerence Machine: Parts 3-5** — Documents the weaponisation pipeline, proposes DeLimerence as the defensive response, details the anti-dependency architecture, and frames the dual-use problem. Provides the product specification, stakeholder landscape, and strategic rationale.

### Appendix B: Key Design Constraints from Source Documents

The following anti-dependency architecture features are referenced throughout this stakeholder analysis as they directly influence multiple stakeholder relationships:

1. Session limits (20 exchanges per conversation)
2. Cooldown periods (8 hours minimum between sessions)
3. No persona (labelled "Tool", no name/avatar/personality)
4. Anti-warmth system prompt
5. Action commitment gate (end-of-session real-world action)
6. Graduated intervention (therapist referral after 10 sessions)
7. Phase-aware responses (initiation, crystallisation, deterioration, resolution)
8. Ritual tracking (persistent, cross-session)
9. Psychoeducation in context (neuroscience at the moment of activation)

---

## External References

> This section provides traceability from generated content back to source documents.

### Document Register

| Doc ID | Filename | Type | Source Location | Description |
|--------|----------|------|-----------------|-------------|
| LM12 | part-1-2-the-limerence-machine.md | Article | 000-global/external/ | The Limerence Machine Parts 1-2: neuroscience of limerence and AI companion industry analysis |
| LM35 | part-3-5-the-limerence-machine.md | Article | 000-global/external/ | The Limerence Machine Parts 3-5: weaponisation, DeLimerence design, and dual-use problem |

### Citations

| Citation ID | Doc ID | Page/Section | Category | Quoted Passage |
|-------------|--------|--------------|----------|----------------|
| LM12-C1 | LM12 | Part One | Stakeholder Need | "intrusive thoughts about the LO can occupy up to 85% of waking hours" |
| LM12-C2 | LM12 | The three endings | Design Decision | "Insight alone is insufficient... This understanding does not stop the neurochemistry. Behavioural intervention is required." |
| LM12-C3 | LM12 | Limerence (intro) | Risk Factor | "compromises executive function, depletes serotonin, and creates addiction-like dependency" |
| LM12-C4 | LM12 | Anyone can experience it | Stakeholder Need | "many limerents have happy, securely attached long-term partnerships, only to be blindsided by someone who triggers the response" |
| LM35-C1 | LM35 | Part Four (intro) | Business Requirement | "a conversational tool built as a deliberate inversion of the companion AI model" |
| LM35-C2 | LM35 | Part Five | Risk Factor | "Publishing this analysis, including the Wardley map of the exploitation pipeline, makes the threat legible but also makes the playbook visible" |
| LM35-C3 | LM35 | Anti-dependency architecture | Design Decision | "preventing users from becoming limerent toward the recovery tool itself... a near-certainty if the tool is designed with the warm, available, affirming presence that characterises companion AIs" |
| LM35-C4 | LM35 | Clinical framework | Functional Requirement | "The only published clinical case study on limerence treatment (Wyant, 2021)... Over nine months, time spent on rituals dropped from over eight hours to ten minutes" |
| LM35-C5 | LM35 | Why a chatbot? | Stakeholder Need | "Limerence produces its most acute distress at 3am, when a therapist is not available, when friends are asleep" |
| LM35-C6 | LM35 | Psychoeducation delivery | Functional Requirement | "Knowing that what you are experiencing is a dopamine dysregulation rather than destiny... creates cognitive distance from the experience" |
| LM35-C7 | LM35 | Conclusion | Business Requirement | "a cognitive pattern interrupter that uses the clinical literature on limerence, CBT, and ERP to help people recognise and recover from obsessive attachment" |
| LM35-C8 | LM35 | Part Five | Risk Factor | "The romance scam industry generated over $1.3 billion in reported losses in the United States alone in 2022" |
| LM35-C9 | LM35 | Part Five | Business Requirement | "The question is not whether AI-enabled limerence exploitation will occur. It is whether the defensive response will be ready when it does." |
| LM35-C10 | LM35 | Graduated intervention | Functional Requirement | "After ten sessions, the tool explicitly asks whether the user is also working with a human therapist" |
| LM35-C11 | LM35 | No persona | Design Decision | "The AI is labelled 'Tool' in the interface. It has no name, no avatar, no personality." |
| LM35-C12 | LM35 | Phase-aware responses | Functional Requirement | "Someone in the crystallisation phase... needs aggressive reality-testing. Someone in the deterioration phase... needs grief support and relapse prevention." |
| LM35-C13 | LM35 | Part Five (intro) | Risk Factor | "limerence is a neurochemical mechanism that can be deliberately triggered, sustained, or interrupted" |
| LM35-C14 | LM35 | Part Five | Risk Factor | "The argument for publication is the same argument that drives responsible disclosure in cybersecurity" |
| LM35-C15 | LM35 | Behavioural activation | Functional Requirement | "what the Living with Limerence community calls 'purposeful living'" |
| LM35-C16 | LM35 | Awareness | Stakeholder Need | "Law enforcement, safeguarding professionals, and platform operators need to understand limerence as an attack vector" |
| LM35-C17 | LM35 | From external to internal coercion | Risk Factor | "In a limerence-based exploitation model, the victim does not need to be threatened into compliance. Their own neurochemistry does the enforcement." |
| LM35-C18 | LM35 | Scale and the CSEA connection | Risk Factor | "children and young people, who are neurologically more vulnerable to limerent attachment" |
| LM35-C19 | LM35 | Detection | Functional Requirement | "Platforms need mechanisms to identify AI-driven intermittent reinforcement patterns in user interactions... This is a tractable signal processing problem." |
| LM35-C20 | LM35 | Stage 1 | Risk Factor | "An AI-driven persona makes contact with the target through a dating app, social media platform, or companion chatbot" |

### Unreferenced Documents

*All source documents were cited.*

---

**Generated by**: ArcKit `/arckit:stakeholders` command
**Generated on**: 2026-04-06
**ArcKit Version**: 4.6.3
**Project**: DeLimerence (Project 001)
**Model**: Claude Opus 4.6 (1M context)
