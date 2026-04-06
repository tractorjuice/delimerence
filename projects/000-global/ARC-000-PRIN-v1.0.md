# Enterprise Architecture Principles: DeLimerence

> **Template Origin**: Official | **ArcKit Version**: 4.6.4-rc.1 | **Command**: `/arckit:principles`

## Document Control

| Field | Value |
|-------|-------|
| **Document ID** | ARC-000-PRIN-v1.0 |
| **Document Type** | Enterprise Architecture Principles |
| **Project** | DeLimerence Enterprise (Project 000) |
| **Classification** | OFFICIAL |
| **Status** | DRAFT |
| **Version** | 1.0 |
| **Created Date** | 2026-04-06 |
| **Last Modified** | 2026-04-06 |
| **Review Cycle** | Annual |
| **Next Review Date** | 2026-10-06 |
| **Owner** | Mark Craddock, Product Owner |
| **Reviewed By** | PENDING |
| **Approved By** | PENDING |
| **Distribution** | All project teams, Clinical Advisory Board |
| **ArcKit Version** | 4.6.4-rc.1 |

## Revision History

| Version | Date | Author | Changes | Approved By | Approval Date |
|---------|------|--------|---------|-------------|---------------|
| 1.0 | 2026-04-06 | ArcKit AI | Initial creation from `/arckit:principles` command | PENDING | PENDING |

---

## 1. Executive Summary

### 1.1 Purpose

This document establishes the enterprise architecture principles that govern all architectural decisions for the DeLimerence programme. These principles apply across all projects (Project 000 global scope and Project 001 product scope) and must be referenced in all Architecture Decision Records (ADRs), design documents, and vendor evaluations.

DeLimerence is an anti-dependency conversational AI tool for limerence recovery. It processes special category health data from psychologically vulnerable users. These principles exist to ensure that every architectural decision protects users, enforces anti-dependency, satisfies regulatory requirements, and advances the clinical mission.

### 1.2 Scope

These principles apply to:

- All software architecture decisions across the DeLimerence programme
- All infrastructure and deployment decisions
- All third-party integrations and vendor selections
- All AI/ML model selection and configuration decisions
- All data architecture and storage decisions

### 1.3 Authority

These principles carry governance authority. Deviation from any principle requires a formal exception process (see Section 9). All ADRs MUST demonstrate compliance with applicable principles or document an approved exception.

### 1.4 Principle Summary

| ID | Principle | Category | Priority |
|----|-----------|----------|----------|
| PRIN-001 | Anti-Dependency by Design | Strategic | P1 - Mandatory |
| PRIN-002 | Clinical Safety First | Strategic | P1 - Mandatory |
| PRIN-003 | Supplement, Not Replace | Strategic | P1 - Mandatory |
| PRIN-004 | Data Residency and Sovereignty | Data | P1 - Mandatory |
| PRIN-005 | Privacy by Design and Data Minimisation | Data | P1 - Mandatory |
| PRIN-006 | Special Category Data Protection | Data | P1 - Mandatory |
| PRIN-007 | Zero-Retention Third-Party Processing | Integration | P1 - Mandatory |
| PRIN-008 | Graceful Degradation | Integration | P2 - Important |
| PRIN-009 | Availability for Crisis Moments | Quality Attribute | P2 - Important |
| PRIN-010 | Outcome Velocity Over Engagement Depth | Quality Attribute | P1 - Mandatory |
| PRIN-011 | Clinical Governance for AI Behaviour | Development Practices | P1 - Mandatory |
| PRIN-012 | Transparent AI | Development Practices | P1 - Mandatory |
| PRIN-013 | Regulatory Engagement Before Feature Launch | Regulatory & Compliance | P1 - Mandatory |
| PRIN-014 | Responsible Dual-Use Disclosure | Regulatory & Compliance | P2 - Important |

### 1.5 Traceability

These principles are derived from and traceable to:

- **ARC-001-REQ-v1.0** — Business and Technical Requirements (50 requirements across 5 categories)
- **ARC-001-STKE-v1.0** — Stakeholder Analysis (goals G-1 through G-5, outcomes O-1 through O-4)
- **ARC-001-RISK-v1.0** — Risk Register (15 risks across 6 categories, particularly R-001, R-002, R-003)
- **ARC-001-ANAL-v1.0** — Governance Analysis Report (finding: "Principles Compliance: N/A — no principles document")
- **Source research** — The Limerence Machine articles [LM35-C1 through LM35-C8]

---

## 2. Strategic Principles

### PRIN-001: Anti-Dependency by Design

**Statement**: All user-facing systems MUST be architecturally designed to prevent dependency formation through structural constraints enforced at infrastructure level.

**Rationale**: DeLimerence exists to counter attachment. If the tool itself creates new attachment, it becomes the problem it purports to solve. This is not a feature-level concern — it is the existential product risk (R-001 in ARC-001-RISK-v1.0). Limerence involves involuntary attachment mediated by intermittent reinforcement, emotional presence, and perceived reciprocity. The architecture must structurally prevent the tool from providing any of these triggers.

**Implications**:

- Session duration limits MUST be enforced server-side, not client-side, to prevent circumvention
- Cooldown periods between sessions MUST be enforced at the infrastructure level
- The AI MUST NOT adopt a persona, use a human name, or simulate emotional warmth
- Action commitment gates MUST require users to commit to real-world actions before continuing
- No notification systems that could create anticipation or intermittent reinforcement patterns
- All anti-dependency constraints MUST be enforced server-side; client-side enforcement is insufficient as it can be bypassed

**Validation Gates**:

- [ ] Session limits are enforced by backend services, not frontend timers
- [ ] Cooldown enforcement has been tested for circumvention (multiple accounts, session replay, API direct access)
- [ ] AI response tone has been reviewed by Clinical Advisory Board for warmth/attachment risk
- [ ] No push notifications, streaks, or engagement-reinforcing patterns exist in any user interface
- [ ] Action commitment gates are present and enforced before session continuation

**Common Violations**:

- Implementing session limits in client-side code only (user can modify)
- Adding "welcome back" messaging that creates anticipation
- Allowing unlimited session frequency without cooldown
- Using engagement metrics (DAU, session length) as success indicators
- Giving the AI a name, avatar, or personality traits

**Traceability**: R-001, FR-001 through FR-009, Goal G-4, Outcome O-2

---

### PRIN-002: Clinical Safety First

**Statement**: All AI-generated responses MUST pass through a multi-layer safety filter before delivery to users. No unfiltered AI output SHALL reach users under any circumstances.

**Rationale**: Users of this system are psychologically vulnerable — they are experiencing involuntary attachment that compromises executive function [LM35-C3]. An AI-generated response that validates limerent thinking, simulates emotional reciprocity, makes diagnostic claims, or fails to detect a crisis could cause real psychological harm. Safety is not a feature — it is the architectural foundation. Risk R-004 (LLM produces clinically harmful response) has a residual risk score of 12 (Medium) only because multi-layer safety filters are assumed to be in place.

**Implications**:

- Defence-in-depth safety architecture: system prompt constraints, output filters, and post-generation review layers
- Warmth detection filters MUST flag and block responses that simulate emotional connection
- Diagnostic claim blocking MUST prevent the system from diagnosing any condition
- Crisis detection MUST identify indicators of self-harm, suicidal ideation, or acute distress and route to appropriate resources
- Safety filters MUST operate independently of the AI model — they cannot rely solely on prompt engineering
- All safety filter decisions MUST be logged for clinical audit

**Validation Gates**:

- [ ] Multi-layer safety filter architecture is documented and implemented
- [ ] Safety filter catch rate exceeds 99% on adversarial test suite
- [ ] Crisis detection has been tested against validated crisis language datasets
- [ ] Warmth detection has been calibrated and approved by Clinical Advisory Board
- [ ] Safety filter operates independently of AI model (not solely prompt-dependent)
- [ ] Clinical Advisory Board has signed off on safety protocols

**Common Violations**:

- Relying solely on system prompt instructions for safety (single point of failure)
- Deploying AI model updates without re-running safety test suites
- Treating safety filters as optional in development/staging environments
- Failing to log safety filter activations for clinical audit
- Assuming the AI model will reliably follow safety instructions without independent verification

**Traceability**: R-004, NFR-001 through NFR-005, Goal G-4

---

### PRIN-003: Supplement, Not Replace

**Statement**: Systems MUST explicitly position themselves as supplements to professional therapy, never as replacements. The architecture MUST structurally prevent the system from occupying a therapist role.

**Rationale**: Trust from mental health professionals is essential for the long-term viability of the tool (Stakeholder SD-3 in ARC-001-STKE-v1.0). If the tool is perceived as replacing therapy, it will face opposition from clinical professionals, regulatory bodies, and mental health charities. More critically, users who treat the tool as a therapy replacement may delay seeking professional help when they need it. The tool must actively push users toward professional support rather than absorbing their therapeutic needs.

**Implications**:

- "Not a therapist" messaging MUST appear during onboarding and at regular intervals within sessions
- The system MUST NOT provide treatment plans, formal assessments, or clinical recommendations
- Graduated referral pathways MUST be built into the conversation flow, escalating toward professional support as distress indicators increase
- The system MUST NOT make diagnostic claims about limerence or any other condition
- Session architecture MUST be designed to complement, not compete with, therapy schedules
- All content MUST be framed as psychoeducation and self-help, not clinical intervention

**Validation Gates**:

- [ ] "Not a therapist" disclaimers appear in onboarding and are repeated within sessions
- [ ] No response template or system prompt contains diagnostic language
- [ ] Referral pathways to professional services are documented and functional
- [ ] Clinical Advisory Board has confirmed the tool does not cross the therapy boundary
- [ ] User research confirms users understand the tool is supplementary

**Common Violations**:

- Omitting disclaimers to reduce friction in the user experience
- Using clinical terminology ("treatment", "diagnosis", "therapy session") in user-facing content
- Building features that replace rather than supplement professional support (e.g., detailed mental health assessments)
- Allowing users to use the tool as their sole source of mental health support without referral prompts

**Traceability**: R-002 (MHRA classification), BR-003, FR-010, Stakeholder SD-3

---

## 3. Data Principles

### PRIN-004: Data Residency and Sovereignty

**Statement**: All user data MUST be stored and processed within the United Kingdom. No user data SHALL be transferred to, processed in, or accessible from jurisdictions outside the UK without explicit regulatory approval.

**Rationale**: DeLimerence processes special category health data under UK GDPR Article 9. Cross-border data transfers introduce compliance risk, regulatory complexity, and potential enforcement exposure (R-003). UK data residency simplifies the regulatory position, reduces ICO scrutiny, and provides users with confidence that their sensitive health disclosures are protected under UK jurisdiction. The UK Adequacy Regulations post-Brexit create specific requirements for international transfers that are avoided entirely by UK-resident processing.

**Implications**:

- All infrastructure hosting user data MUST be physically located in UK data centres
- AI/ML processing that involves user data MUST occur within UK-resident infrastructure
- Data processing agreements with third parties MUST contractually require UK data residency
- Architecture designs MUST specify deployment regions and confirm UK residency
- Monitoring and logging systems that capture user data MUST also be UK-resident
- Disaster recovery and backup infrastructure MUST maintain UK residency requirements

**Validation Gates**:

- [ ] All infrastructure components are confirmed as UK-hosted (deployment region documented)
- [ ] Third-party DPAs include UK data residency clauses
- [ ] No data egress paths exist to non-UK jurisdictions (network architecture reviewed)
- [ ] Backup and DR infrastructure confirmed as UK-resident
- [ ] AI/ML processing confirmed as UK-resident (no data sent to overseas model endpoints without DPA controls)

**Common Violations**:

- Using default cloud deployment regions that are outside the UK
- Failing to verify that third-party SaaS tools process data within the UK
- Sending telemetry, logs, or error reports containing user data to non-UK endpoints
- Using AI model APIs hosted outside the UK without confirming zero-retention and DPA coverage
- Assuming cloud provider "EU region" satisfies UK residency requirements (it does not post-Brexit)

**Traceability**: R-003, DR-001, DR-002, NFR-014, NFR-015

---

### PRIN-005: Privacy by Design and Data Minimisation

**Statement**: Systems MUST collect only the minimum data necessary to deliver the service and MUST implement privacy controls at the architectural level, not as an afterthought.

**Rationale**: UK GDPR Article 25 requires privacy by design and by default. DeLimerence users have compromised executive function due to the neurochemical effects of limerence [LM35-C3], which means they may disclose more than they intend or consent to data processing without fully understanding the implications. The architecture must protect users from themselves by minimising what is collected and ensuring that consent mechanisms account for diminished decision-making capacity.

**Implications**:

- Data collection MUST be limited to what is strictly necessary for the defined purpose (data minimisation)
- Field-level encryption MUST be applied to sensitive content fields (ritual descriptions, emotional disclosures)
- Consent architecture MUST be designed for users with compromised executive function — plain language, layered consent, ability to withdraw without friction
- Right to deletion MUST be fulfilled within 30 days, with cryptographic deletion verification
- Data retention periods MUST be defined and enforced for all data categories
- Anonymisation MUST be applied before any data is used for research or analytics
- Privacy Impact Assessments MUST be conducted before introducing new data collection

**Validation Gates**:

- [ ] Data inventory documents all data collected, with justification for each field
- [ ] Field-level encryption is implemented for sensitive content
- [ ] Consent flow has been reviewed for accessibility by users with compromised capacity
- [ ] Right to deletion is implemented and tested (confirmed within 30-day SLA)
- [ ] Retention periods are defined and automated enforcement is in place
- [ ] DPIA has been completed and submitted to DPO

**Common Violations**:

- Collecting data "in case we need it later" without a defined purpose
- Implementing privacy controls at the application layer only, without architectural enforcement
- Using generic consent forms that assume full decision-making capacity
- Retaining data beyond defined retention periods due to lack of automated enforcement
- Treating anonymisation as optional for internal analytics

**Traceability**: R-003, DR-001 through DR-004, NFR-014, NFR-015, UK GDPR Articles 5, 17, 25

---

### PRIN-006: Special Category Data Protection

**Statement**: All health-related data MUST be encrypted at rest and in transit with field-level encryption for sensitive content. The lawful basis for processing special category data under Article 9 MUST be established and documented before any processing begins.

**Rationale**: Ritual tracking data, phase assessments, session transcripts, and emotional disclosures all constitute special category health data under UK GDPR Article 9. This is the highest protection category under data protection law. A data breach involving this content would cause severe reputational damage (R-003 residual risk score: 15, High) and potential regulatory action. The ICO has signalled increased scrutiny of AI systems processing health data.

**Implications**:

- AES-256 equivalent encryption at rest for all data stores containing health data
- TLS 1.3 or later for all data in transit
- Field-level encryption for ritual descriptions, phase assessments, and emotional disclosure content
- Article 9 lawful basis MUST be established (explicit consent or substantial public interest) and documented
- Data Protection Impact Assessment (DPIA) MUST be completed before processing begins
- Breach notification procedures MUST be in place (72-hour ICO notification, user notification without undue delay)
- Access controls MUST enforce least-privilege access to special category data

**Validation Gates**:

- [ ] Encryption at rest confirmed (AES-256 equivalent or stronger)
- [ ] TLS 1.3+ confirmed for all data in transit
- [ ] Field-level encryption implemented for identified sensitive fields
- [ ] Article 9 lawful basis documented and approved by DPO
- [ ] DPIA completed and submitted
- [ ] Breach notification procedures documented and tested
- [ ] Access controls implement least-privilege for special category data

**Common Violations**:

- Using transport-level encryption only without encrypting data at rest
- Failing to apply field-level encryption to sensitive content within otherwise encrypted databases
- Processing special category data before establishing and documenting the Article 9 lawful basis
- Treating DPIA as a one-time document rather than a living assessment updated with architectural changes
- Granting broad database access to development teams without least-privilege controls

**Traceability**: R-003, DR-001 through DR-004, NFR-014, UK GDPR Articles 9, 32, 33, 34, 35

---

## 4. Integration Principles

### PRIN-007: Zero-Retention Third-Party Processing

**Statement**: All third-party AI/ML processing MUST operate under data processing agreements that contractually prohibit provider storage, retention, or use of user content for any purpose including model training.

**Rationale**: User conversations with DeLimerence contain highly sensitive health disclosures — ritual descriptions, emotional states, attachment patterns, and crisis indicators. If a third-party AI provider retains this content, it creates uncontrolled copies of special category health data outside the data controller's governance. This violates data minimisation principles, creates breach surface area, and risks user content appearing in model training data. Risk R-003 mitigation depends on zero-retention guarantees from all processors.

**Implications**:

- Data Processing Agreements MUST be executed with all third-party processors before integration
- DPAs MUST include explicit zero-retention clauses — no storage of prompts, completions, or metadata beyond the processing transaction
- DPAs MUST include explicit prohibition on using user data for model training or improvement
- Provider compliance with zero-retention MUST be validated (contractual audit rights, compliance certifications)
- Architecture MUST be designed to allow provider substitution if a provider violates zero-retention terms
- Logging of data sent to third-party processors MUST be maintained for audit purposes (without duplicating sensitive content)

**Validation Gates**:

- [ ] DPA executed with every third-party processor
- [ ] Zero-retention clause confirmed in each DPA
- [ ] No-training clause confirmed in each DPA
- [ ] Provider compliance validation approach documented (audit rights, certifications)
- [ ] Architecture supports provider substitution without user impact
- [ ] Audit log of third-party processing transactions is maintained

**Common Violations**:

- Integrating with a third-party AI provider before executing a DPA
- Accepting provider terms of service without confirming zero-retention for enterprise/API usage
- Assuming "enterprise tier" automatically means zero-retention (must be contractually confirmed)
- Sending user data to third-party processors in development/testing environments without DPA coverage
- Failing to re-validate DPA terms when providers update their terms of service

**Traceability**: R-003, R-006, INT-001 through INT-003, DR-002

---

### PRIN-008: Graceful Degradation

**Statement**: Systems MUST degrade gracefully when external dependencies fail, providing safe fallback content with crisis resources rather than broken interfaces or error states.

**Rationale**: Limerence distress is not time-bound. A user in acute distress at 3am who encounters a broken tool with no fallback is left without the crisis resources the tool promises to provide. An error page is not acceptable when the alternative is a person in psychological crisis with no support. Graceful degradation is a clinical safety requirement, not merely a quality-of-life feature.

**Implications**:

- Circuit breaker patterns MUST be implemented for all external service dependencies
- Static fallback content MUST be available when AI processing is unavailable, including crisis helpline numbers and basic grounding exercises
- Cooldown timers and session management MUST operate independently of AI availability
- Anti-dependency constraints MUST remain enforced even when the system is in degraded mode
- Users MUST be informed when they are receiving fallback content rather than AI-generated responses
- Fallback content MUST be reviewed and approved by the Clinical Advisory Board

**Validation Gates**:

- [ ] Circuit breaker patterns implemented for all external dependencies
- [ ] Static fallback content includes crisis resources (helpline numbers, grounding exercises)
- [ ] Fallback content has been reviewed by Clinical Advisory Board
- [ ] Degraded mode has been tested (external dependency failure simulation)
- [ ] Anti-dependency constraints remain enforced in degraded mode
- [ ] Cooldown timers operate independently of AI service availability

**Common Violations**:

- Displaying generic error pages when AI services are unavailable
- Removing anti-dependency constraints in degraded mode to "improve the experience"
- Failing to include crisis resources in fallback content
- Not testing degraded mode scenarios during development
- Assuming external services will always be available and not implementing fallback paths

**Traceability**: R-004, R-006, NFR-006 through NFR-008, Outcome O-2

---

## 5. Quality Attribute Principles

### PRIN-009: Availability for Crisis Moments

**Statement**: User-facing systems MUST achieve minimum 99.9% availability, measured monthly. Planned maintenance MUST be scheduled outside peak distress hours.

**Rationale**: Limerence produces acute distress episodes that occur unpredictably and at any hour, with evidence suggesting late-night and early-morning peaks when professional support is unavailable [LM35-C4]. A system designed for crisis moments must be available during crisis moments. 99.9% availability allows for approximately 43 minutes of downtime per month — still a significant risk window, but a pragmatic target for a startup-scale operation.

**Implications**:

- Architecture MUST support multi-region or multi-availability-zone deployment for redundancy
- Automated failover MUST be implemented for all critical path components
- Planned maintenance windows MUST be scheduled during lowest-usage periods (typically mid-morning weekdays based on limerence distress patterns)
- Health monitoring MUST provide real-time alerting for availability drops
- Recovery Time Objective (RTO) MUST be defined and tested: target 15 minutes or less
- Recovery Point Objective (RPO) MUST be defined: target zero data loss for active sessions

**Validation Gates**:

- [ ] 99.9% availability target documented in SLA/SLO definitions
- [ ] Multi-region or multi-AZ deployment architecture is in place
- [ ] Automated failover tested and confirmed functional
- [ ] Maintenance windows defined and communicated (outside peak distress hours)
- [ ] RTO tested and confirmed within 15-minute target
- [ ] Health monitoring and alerting operational

**Common Violations**:

- Scheduling maintenance during evening/night hours when distress episodes peak
- Deploying to a single availability zone without redundancy
- Defining availability targets without implementing monitoring to measure them
- Treating availability as an infrastructure concern only (application-level failures also count)
- Not testing failover procedures regularly

**Traceability**: R-006, NFR-006, NFR-007, NFR-008, Goal G-1

---

### PRIN-010: Outcome Velocity Over Engagement Depth

**Statement**: Success metrics MUST measure recovery velocity — how quickly users improve and disengage — not engagement depth. Declining usage MUST be treated as the primary success indicator.

**Rationale**: Anti-dependency architecture fundamentally inverts conventional product metrics. In a standard SaaS product, declining daily active users signals failure. In DeLimerence, declining daily active users signals success — users are recovering and no longer need the tool. If the architecture team optimises for engagement metrics (DAU, session length, retention), they will build a system that contradicts the clinical mission and creates the dependency the tool exists to prevent [LM35-C1]. This principle is the metric-level expression of PRIN-001.

**Implications**:

- Analytics architecture MUST track recovery-oriented metrics: ritual reduction rate, time-to-resolution, declining session frequency, action commitment completion rate
- Analytics architecture MUST NOT track or optimise for DAU, retention rate, session length, or any engagement-depth metric
- A/B testing MUST NOT optimise for engagement — test variations must be evaluated against recovery velocity
- Dashboards MUST present recovery metrics prominently; engagement metrics (if tracked for operational purposes) must be clearly labelled as operational, not success indicators
- Stakeholder reporting MUST use recovery velocity as the primary KPI

**Validation Gates**:

- [ ] Recovery-oriented metrics defined and implemented (ritual reduction, time-to-resolution, declining session frequency)
- [ ] No engagement-depth metrics (DAU, retention, session length) are used as success KPIs
- [ ] A/B testing framework evaluates against recovery velocity, not engagement
- [ ] Stakeholder dashboards present recovery metrics as primary indicators
- [ ] Clinical Advisory Board has reviewed and approved the metrics framework

**Common Violations**:

- Reporting DAU or retention rate as success metrics to stakeholders or investors
- Optimising A/B tests for session length or return frequency
- Building features designed to increase engagement (notifications, streaks, gamification)
- Treating a user who stops using the tool as "churned" rather than "recovered"
- Benchmarking against conventional SaaS engagement metrics

**Traceability**: R-001, BR-001, BR-002, Goal G-2, Goal G-4, Outcome O-1, Outcome O-2

---

## 6. Development Practices Principles

### PRIN-011: Clinical Governance for AI Behaviour

**Statement**: All changes to AI system prompts, response protocols, safety filter rules, and therapeutic content MUST be version-controlled and MUST require Clinical Advisory Board approval before deployment to production.

**Rationale**: The system prompt is the clinical core of DeLimerence. It defines the therapeutic approach, the boundaries of the tool's behaviour, the safety constraints, and the anti-dependency architecture. An unreviewed change to the system prompt is equivalent to an unreviewed change to a medical protocol — it could alter the therapeutic approach in ways that cause harm. Risk R-004 (LLM produces clinically harmful response) depends on clinical review as a key mitigation.

**Implications**:

- System prompts MUST be stored in version control with full change history
- All changes to system prompts, safety filter rules, or therapeutic content MUST follow a clinical change management process
- Clinical Advisory Board MUST review and approve changes before production deployment
- Rollback capability MUST allow reversion to the previous approved version within 15 minutes
- Emergency rollback authority MUST be defined (who can roll back without full board approval in a crisis)
- A clinical change log MUST be maintained for audit purposes

**Validation Gates**:

- [ ] System prompts are in version control with full history
- [ ] Clinical change management process is documented and followed
- [ ] Clinical Advisory Board approval is required before production deployment
- [ ] Rollback tested and confirmed within 15-minute target
- [ ] Emergency rollback authority defined and documented
- [ ] Clinical change log is maintained and auditable

**Common Violations**:

- Editing system prompts directly in production without version control
- Deploying prompt changes without Clinical Advisory Board review ("it's just a small tweak")
- Failing to test rollback procedures
- Not maintaining a clinical change log
- Granting production system prompt access to individuals without clinical review authority

**Traceability**: R-004, FR-001 through FR-009, NFR-001 through NFR-005, Goal G-4

---

### PRIN-012: Transparent AI

**Statement**: AI systems MUST consistently and prominently identify themselves as software tools. The system MUST NOT simulate human presence, emotional connection, or therapeutic relationship.

**Rationale**: Transparency is the primary architectural defence against limerence transfer (R-001). If a user perceives the AI as human, as emotionally present, or as a relationship partner, the tool becomes a limerence trigger rather than a recovery aid. Transparency prevents attachment formation and maintains user trust. This principle operationalises PRIN-001 at the interaction design level.

**Implications**:

- The AI MUST be labelled as "Tool" or equivalent — never given a human name
- No avatar, profile picture, or visual representation that suggests human presence
- No personality traits, emotional expressions, or simulated empathy
- Regular transparency reminders MUST appear within sessions ("I am a software tool, not a person")
- Response style MUST be direct, functional, and deliberately clinical — not warm, conversational, or companionate
- Typing indicators, read receipts, or other presence signals that simulate human interaction MUST NOT be used

**Validation Gates**:

- [ ] AI is identified as "Tool" (or equivalent non-human label) in all interfaces
- [ ] No avatar, human name, or personality traits are present
- [ ] Transparency reminders appear at defined intervals within sessions
- [ ] Response style has been reviewed for warmth/attachment risk by Clinical Advisory Board
- [ ] No typing indicators, read receipts, or presence signals are implemented
- [ ] User testing confirms users understand they are interacting with software

**Common Violations**:

- Giving the AI a human name to make it "more approachable"
- Adding typing indicators to make responses feel more natural
- Using first-person emotional language ("I care about your recovery")
- Designing the interface to resemble a messaging app with a human contact
- Softening the AI's tone to increase user satisfaction scores (at the cost of attachment risk)

**Traceability**: R-001, FR-001, FR-002, FR-003, PRIN-001, Goal G-4, Outcome O-2

---

## 7. Regulatory and Compliance Principles

### PRIN-013: Regulatory Engagement Before Feature Launch

**Statement**: Features that may cross regulatory boundaries MUST be assessed against applicable regulatory frameworks before deployment. No feature SHALL be launched that could trigger medical device classification without prior regulatory assessment.

**Rationale**: MHRA classification is consequential. If DeLimerence is classified as a medical device, it adds 12-18 months to the regulatory pathway and fundamentally changes the compliance architecture (R-002 residual risk score: 16, the highest residual risk in the register). The phased launch approach defined in the project strategy depends on understanding exactly where the regulatory boundaries lie. A feature that inadvertently crosses the MHRA threshold could force retrospective compliance with the full medical device regulatory framework.

**Implications**:

- Every new feature MUST undergo a regulatory boundary assessment before development begins
- Features that approach regulatory boundaries MUST be discussed with MHRA through pre-submission engagement
- The phased launch approach MUST be maintained: Phase 1 (psychoeducation only) carries lower regulatory risk than Phase 2 (personalised interventions)
- Regulatory boundary assessments MUST be documented and traceable to the feature they assess
- Legal and regulatory advice MUST be sought before making claims about clinical efficacy
- Marketing and user-facing content MUST be reviewed for inadvertent medical claims

**Validation Gates**:

- [ ] Regulatory boundary assessment completed for each feature before development
- [ ] MHRA pre-submission engagement planned or completed for features near regulatory boundaries
- [ ] Phased launch approach maintained (Phase 1 features carry lower regulatory risk)
- [ ] Legal review completed for any content making efficacy claims
- [ ] Marketing content reviewed for inadvertent medical claims
- [ ] Regulatory boundary assessments documented and traceable

**Common Violations**:

- Building personalised intervention features before confirming MHRA classification
- Making efficacy claims ("clinically proven", "evidence-based treatment") without regulatory clearance
- Treating regulatory assessment as a post-launch compliance activity
- Assuming that labelling the tool as "wellness" avoids all medical device regulation
- Launching features in beta without regulatory assessment ("it's just a test")

**Traceability**: R-002, BR-003, Goal G-3, Outcome O-3

---

### PRIN-014: Responsible Dual-Use Disclosure

**Statement**: Knowledge and research that enables both defensive and offensive applications MUST be published within a responsible disclosure framework with ethics review before release.

**Rationale**: The same limerence knowledge that enables recovery tools also enables exploitation. DeLimerence's research into how limerence can be induced, maintained, and weaponised [LM35-C7] has dual-use potential — it describes exactly how bad actors could use AI to create artificial limerence for sextortion, romance fraud, and CSEA at scale. Publication must maximise defensive value while minimising the risk of providing a how-to guide for exploitation. Risk R-005 (publication backlash on exploitation analysis) has a residual risk score of 12 (Medium).

**Implications**:

- Ethics Review Panel MUST sign off on all publications that include limerence induction, weaponisation, or exploitation analysis
- Safeguarding organisations (NCA, NCSC, IWF, relevant charities) MUST be pre-briefed before public disclosure of exploitation techniques
- All dual-use content MUST be framed defensively — describing what to detect and defend against, not how to attack
- Publication timing MUST allow defensive measures to be in place before offensive techniques are publicly described
- Responsible disclosure timelines MUST be defined and followed
- Internal research documents containing offensive techniques MUST be classified and access-controlled

**Validation Gates**:

- [ ] Ethics Review Panel has reviewed and approved the publication
- [ ] Safeguarding organisations have been pre-briefed
- [ ] Content is framed defensively (detection and defence, not attack methodology)
- [ ] Defensive measures are in place before offensive techniques are disclosed
- [ ] Responsible disclosure timeline has been followed
- [ ] Internal research documents are classified and access-controlled

**Common Violations**:

- Publishing exploitation analysis without ethics review ("it's already in the public domain")
- Framing dual-use content offensively (describing how to induce limerence rather than how to detect it)
- Failing to pre-brief safeguarding organisations before publication
- Publishing detailed technical attack methodologies without corresponding defensive guidance
- Not classifying internal research documents that contain offensive techniques

**Traceability**: R-005, BR-005, Goal G-5, Outcome O-4, Stakeholder SD-5 (Safeguarding Organisations)

---

## 8. Principle Interaction Matrix

Principles do not operate in isolation. The following matrix identifies key interactions, reinforcements, and potential tensions between principles.

### 8.1 Reinforcing Relationships

| Principle Pair | Relationship |
|---------------|--------------|
| PRIN-001 + PRIN-012 | Transparent AI reinforces Anti-Dependency — transparency prevents the emotional attachment that dependency requires |
| PRIN-001 + PRIN-010 | Outcome Velocity reinforces Anti-Dependency — measuring recovery prevents optimising for engagement |
| PRIN-002 + PRIN-011 | Clinical Governance reinforces Clinical Safety — review processes prevent unsafe changes from reaching users |
| PRIN-002 + PRIN-008 | Graceful Degradation reinforces Clinical Safety — fallback content ensures safety when primary systems fail |
| PRIN-004 + PRIN-006 | Special Category Protection reinforces Data Residency — UK residency simplifies Article 9 compliance |
| PRIN-005 + PRIN-007 | Zero-Retention reinforces Privacy by Design — preventing third-party retention is a form of data minimisation |
| PRIN-003 + PRIN-013 | Regulatory Engagement reinforces Supplement Not Replace — staying supplementary reduces MHRA classification risk |

### 8.2 Potential Tensions

| Principle Pair | Tension | Resolution |
|---------------|---------|------------|
| PRIN-001 (Anti-Dependency) vs PRIN-009 (Availability) | High availability could enable dependency by ensuring the tool is always available | PRIN-001 takes precedence — availability supports crisis access, but session limits and cooldowns prevent dependency regardless of availability |
| PRIN-004 (UK Residency) vs PRIN-007 (Zero-Retention) | UK residency may limit available AI providers; zero-retention further constrains options | Both are P1 Mandatory — provider selection must satisfy both constraints; accept reduced provider choice |
| PRIN-002 (Clinical Safety) vs PRIN-009 (Availability) | Safety filters add latency; availability requires fast response times | PRIN-002 takes precedence — safety filters must complete before response delivery, even at the cost of latency |
| PRIN-012 (Transparent AI) vs User Experience | Transparency reminders may feel repetitive and reduce perceived helpfulness | PRIN-012 takes precedence — user satisfaction must not come at the cost of attachment risk |

---

## 9. Exception Process

### 9.1 Overview

These principles are mandatory governance constraints. However, exceptional circumstances may require temporary deviation. The exception process exists to ensure that deviations are conscious, documented, time-limited, and approved by appropriate authority.

### 9.2 Exception Process Steps

```
Step 1: FORMAL REQUEST
  - Requestor submits exception request documenting:
    - Which principle(s) require exception
    - Specific deviation requested
    - Business/technical justification
    - Duration of exception (MUST be time-limited)
    - Risk assessment of the deviation
    - Proposed compensating controls

Step 2: IMPACT ASSESSMENT
  - Architecture team assesses:
    - Impact on other principles (see Interaction Matrix, Section 8)
    - Impact on regulatory compliance
    - Impact on clinical safety
    - Impact on user data protection
    - Compensating controls adequacy

Step 3: APPROVAL
  - Required approvers (ALL must approve):
    - Product Owner (Mark Craddock)
    - Clinical Advisory Board representative
  - Additional approvers for specific principles:
    - PRIN-002, PRIN-003, PRIN-011: Full Clinical Advisory Board
    - PRIN-004, PRIN-005, PRIN-006, PRIN-007: Data Protection Officer
    - PRIN-013: Regulatory Advisor
    - PRIN-014: Ethics Review Panel

Step 4: DOCUMENTATION
  - Approved exception MUST be documented in an Architecture Decision Record (ADR)
  - ADR MUST include:
    - Exception justification
    - Approval evidence
    - Compensating controls
    - Expiry date
    - Review schedule
    - Conditions for revocation

Step 5: MONITORING AND REVIEW
  - Exception status reviewed at each architecture review
  - Exception automatically expires on the defined date
  - Extension requires a new exception request (no automatic renewal)
  - Exception MUST be revoked immediately if compensating controls are found to be inadequate
```

### 9.3 Exception Register

| Exception ID | Principle | Requested By | Approved By | Expiry Date | ADR Reference | Status |
|-------------|-----------|--------------|-------------|-------------|---------------|--------|
| *No active exceptions* | | | | | | |

### 9.4 Non-Negotiable Principles

The following principles MUST NOT be subject to exception under any circumstances:

- **PRIN-001** (Anti-Dependency by Design) — This is the existential product principle. Exception would undermine the tool's reason for existence.
- **PRIN-002** (Clinical Safety First) — Safety filters cannot be bypassed or reduced. No exception.
- **PRIN-006** (Special Category Data Protection) — Encryption of health data is a legal requirement. No exception.

---

## 10. Governance and Review

### 10.1 Review Schedule

| Review Type | Frequency | Participants | Purpose |
|------------|-----------|--------------|---------|
| **Annual Review** | Every 12 months (next: 2026-10-06) | Product Owner, Clinical Advisory Board, Architecture Team | Full review of all principles for continued relevance |
| **Triggered Review** | On significant change | Product Owner + relevant stakeholders | Review specific principles affected by regulatory changes, incidents, or new features |
| **Exception Review** | Each architecture review | Architecture Team | Review active exceptions and compensating controls |

### 10.2 Change Process

Changes to this document follow the same governance as any architecture artifact:

1. Proposed changes documented with rationale
2. Impact assessment against existing ADRs and designs
3. Clinical Advisory Board review (for principles affecting clinical safety)
4. Product Owner approval
5. Version increment and revision history update
6. Distribution to all project teams

### 10.3 Compliance Assessment

Compliance with these principles MUST be assessed:

- During ADR creation (each ADR must reference applicable principles)
- During design reviews (HLD and DLD reviews must confirm principle compliance)
- During vendor evaluations (vendor scorecards must assess principle alignment)
- During governance analysis (periodic `/arckit:analyze` runs must include principles compliance scoring)

---

## Appendix A: Glossary

| Term | Definition |
|------|-----------|
| **Anti-dependency** | Architectural approach that structurally prevents users from forming attachment to the tool |
| **Cooldown period** | Enforced waiting period between sessions to prevent compulsive usage |
| **Action commitment gate** | Interface element requiring users to commit to real-world actions before continuing tool use |
| **Limerence** | Involuntary state of intense romantic attachment characterised by intrusive thinking, emotional dependency, and compulsive rituals |
| **Limerence transfer** | Formation of limerent attachment to the tool itself, replacing the original limerent object |
| **Ritual tracking** | Monitoring of limerent behaviours (social media checking, route-taking, mental rehearsal) over time |
| **Phase assessment** | Evaluation of which limerence phase a user is in (infatuation, crystallisation, deterioration, resolution) |
| **Special category data** | UK GDPR classification for sensitive data including health data, requiring Article 9 lawful basis |
| **Zero-retention** | Contractual guarantee that a data processor does not store user content beyond the processing transaction |
| **Warmth detection** | Safety filter that identifies AI responses simulating emotional warmth or connection |
| **Recovery velocity** | Rate at which users reduce limerent symptoms and disengage from the tool |

## Appendix B: Regulatory References

| Reference | Relevance |
|-----------|-----------|
| **UK GDPR** | Data protection framework governing all personal data processing, with Article 9 for special category health data |
| **UK GDPR Article 9** | Lawful basis required for processing special category (health) data |
| **UK GDPR Article 25** | Privacy by design and by default |
| **UK GDPR Article 35** | Data Protection Impact Assessment requirement for high-risk processing |
| **MHRA Software as Medical Device** | Regulatory framework that may apply if DeLimerence is classified as a medical device |
| **NHS Digital Technology Assessment Criteria (DTAC)** | Clinical safety and data protection standards for digital health tools |
| **ICO AI Guidance** | Information Commissioner's Office guidance on AI and data protection |
| **HM Treasury Orange Book** | Risk management framework referenced in risk register methodology |

---

**Generated by**: ArcKit `/arckit:principles` command
**Generated on**: 2026-04-06
**ArcKit Version**: 4.6.4-rc.1
**Project**: DeLimerence Enterprise (Project 000)
**AI Model**: Claude Opus 4.6 (1M context)
**Generation Context**: Principles derived from ARC-001-REQ-v1.0, ARC-001-STKE-v1.0, ARC-001-RISK-v1.0, and ARC-001-ANAL-v1.0 governance analysis findings
