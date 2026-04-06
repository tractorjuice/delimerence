# Project Requirements: DeLimerence

> **Template Origin**: Official | **ArcKit Version**: 4.6.3 | **Command**: `/arckit:requirements`

## Document Control

| Field | Value |
|-------|-------|
| **Document ID** | ARC-001-REQ-v1.0 |
| **Document Type** | Business and Technical Requirements |
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
| 1.0 | 2026-04-06 | ArcKit AI | Initial creation from `/arckit:requirements` command | PENDING | PENDING |

## Document Purpose

This document defines the business, functional, non-functional, integration, and data requirements for DeLimerence — a conversational AI tool designed to help people recognise and recover from limerence. Requirements are traceable to stakeholder goals defined in ARC-001-STKE-v1.0 and to the source articles describing the anti-dependency architecture and clinical framework.

---

## Executive Summary

### Business Context

DeLimerence is a conversational AI tool built as a deliberate inversion of the companion AI model [LM35-C1]. Where AI companion apps (Replika, Character.ai) deepen emotional attachment through intermittent reinforcement and simulated emotional presence, DeLimerence systematically loosens attachment using CBT, ERP, and psychoeducation grounded in the clinical literature on limerence.

The project exists in the context of two converging threats: the AI companion industry's structural incentive to maximise attachment-driven engagement [LM12-C5], and the weaponisation potential of AI-enabled limerence induction for sextortion, romance fraud, and CSEA at scale [LM35-C7]. DeLimerence is the defensive response — a prototype that demonstrates clinically informed anti-attachment AI.

The only published clinical case study on limerence treatment (Wyant, 2021) demonstrated that CBT techniques adapted from OCD protocols reduced ritual time from 8+ hours to 10 minutes over 9 months [LM35-C4]. DeLimerence operationalises this approach in a conversational format, available 24/7, at the point of crisis.

### Objectives

- Deliver a public beta of the anti-dependency conversational AI tool by Q4 2026 (Goal G-1)
- Demonstrate measurable reduction in limerent rituals within 90 days of use (Goal G-2)
- Establish regulatory pathway (MHRA classification, ICO DPIA) within 6 months (Goal G-3)
- Validate that the anti-dependency architecture prevents user attachment to the tool (Goal G-4)
- Support the broader mission of establishing limerence as a recognised exploitation vector (Goal G-5)

### Expected Outcomes

- 50% reduction in median self-reported daily ritual time within 90 days for engaged users (Outcome O-1)
- Zero reported cases of limerence transfer to the tool within first year of operation (Outcome O-2)
- Full regulatory compliance (MHRA determination, DPIA submission, validated consent) before public launch (Outcome O-3)
- At least 1 safeguarding training programme adopts the limerence threat model by end 2027 (Outcome O-4)

### Project Scope

**In Scope**:

- Conversational AI tool for limerence recovery (web and mobile)
- Anti-dependency architecture (9 structural constraints)
- Phase-aware response system (4 limerence phases)
- Ritual tracking with persistent cross-session storage
- Psychoeducation content delivery engine
- CBT/ERP-based intervention protocols
- Consent and onboarding flows for vulnerable users
- Anonymised outcome data collection for research

**Out of Scope**:

- Diagnosis of limerence or any mental health condition
- Replacement for professional therapy or crisis services
- Detection tools for platform operators (separate project)
- Law enforcement training materials (separate deliverable)
- Treatment of conditions other than limerence
- Integration with electronic health records
- Support for minors (adult-only at launch; age-gating required)

---

## Stakeholders

| Stakeholder | Role | Organization | Involvement Level |
|-------------|------|--------------|-------------------|
| Mark Craddock | Product Owner / Founder | DeLimerence | Decision maker |
| Clinical Advisory Board | Clinical Governance | To be constituted | Protocol approval, safety gates |
| Ethics Review Panel | Ethics & Safety | To be constituted | Dual-use review, pre-launch sign-off |
| Data Protection Officer | Compliance | To be appointed | DPIA, consent architecture |
| Development Team | Engineering | DeLimerence | Implementation |
| UX / Content Design | Design | DeLimerence | Anti-dependency UX, psychoeducation content |
| Mental Health Professionals | Referral Partners | External | Clinical validation, co-design |
| Users in Limerence | Primary Users | General Public | Beta testing, feedback |
| Living with Limerence Community | Peer Support | External | Community consultation, beta testing |

---

## Business Requirements

### BR-001: Deliver Limerence Recovery Tool

**Description**: Build and launch a conversational AI tool that helps people recognise and recover from limerence using clinically grounded CBT/ERP techniques and psychoeducation, available 24/7 on mobile and web.

**Rationale**: Limerence produces acute distress at all hours — particularly at 3am when therapists are unavailable [LM35-C5]. No dedicated digital tool exists for limerence intervention. The defensive application must exist before AI-enabled limerence exploitation scales further [LM35-C9].

**Success Criteria**:

- Public beta launched by Q4 2026 with all 9 anti-dependency features operational
- Clinical advisory board sign-off achieved before public launch
- Tool available 24/7 on web and mobile platforms

**Priority**: MUST_HAVE

**Stakeholder**: Product Owner (SD-2), Users (SD-1) | Goals: G-1, G-2

---

### BR-002: Prevent User Attachment to the Tool

**Description**: The tool must be architecturally designed to prevent users from forming limerent or dependent attachment to it, through structural constraints enforced at the infrastructure level rather than relying solely on conversational behaviour.

**Rationale**: This is the existential risk for the product. A tool designed to counter attachment that instead creates new attachment would be worse than useless — it would replicate the companion AI problem [LM35-C3]. The anti-dependency architecture must be demonstrably effective.

**Success Criteria**:

- Zero reported cases of limerence transfer to the tool within first year
- Declining average session frequency per user over time
- Cooldown compliance rate > 90%
- Clinical advisory board annual safety sign-off

**Priority**: MUST_HAVE

**Stakeholder**: Clinical Advisory Board (SD-4), Ethics Panel (SD-5), Users (SD-1) | Goals: G-4

---

### BR-003: Demonstrate Measurable Clinical Outcomes

**Description**: The tool must produce measurable, trackable improvements in limerent symptoms (ritual time, intrusive thought frequency, distress levels) that can be reported to funders, shared with researchers, and used to build the clinical evidence base.

**Rationale**: The evidence base for limerence treatment is limited to a single case study (Wyant, 2021) [LM35-C4]. Without measurable outcomes, the tool has no clinical credibility, no research value, and no basis for sustainable funding. Outcome velocity (how quickly users recover) is the primary success metric — not engagement depth.

**Success Criteria**:

- 50% reduction in median self-reported daily ritual time within 90 days for users completing 10+ sessions
- Outcome data available in anonymised aggregate form for research partnerships
- Quarterly outcome reports produced for funders and clinical advisory board

**Priority**: MUST_HAVE

**Stakeholder**: Funders (SD-9), Academic Researchers (SD-10), Mental Health Professionals (SD-3) | Goals: G-2

---

### BR-004: Achieve Regulatory Compliance Before Public Launch

**Description**: Obtain MHRA classification determination, complete ICO DPIA submission, establish Article 9 lawful basis for special category data processing, and validate consent architecture for users with potentially compromised executive function — all before public beta launch.

**Rationale**: DeLimerence processes special category health data from psychologically vulnerable users. Regulatory non-compliance risks ICO enforcement, MHRA forced withdrawal, user harm, and loss of stakeholder trust. Early regulatory engagement prevents wasted development on the wrong pathway [STKE G-3].

**Success Criteria**:

- Written MHRA classification determination received
- DPIA completed and submitted to ICO
- Consent architecture validated for compromised executive function
- Article 9 lawful basis confirmed by legal counsel

**Priority**: MUST_HAVE

**Stakeholder**: ICO (SD-7), MHRA (SD-8), DPO | Goals: G-3

---

### BR-005: Position as Supplement to Professional Therapy

**Description**: The tool must be explicitly and consistently positioned as a supplement to professional mental health support, never as a replacement. Messaging, UX, and intervention logic must reinforce this positioning throughout the user journey.

**Rationale**: Mental health professionals will only trust and refer to a tool that does not undermine the therapeutic relationship or make clinical claims beyond its evidence base [STKE SD-3]. Users must understand the tool's limitations to make informed decisions about their care.

**Success Criteria**:

- "Not a therapist" messaging present in onboarding, session headers, and periodic reminders
- Graduated intervention: tool explicitly asks about therapist involvement after 10 sessions [LM35-C10]
- No diagnostic claims made anywhere in the tool
- Mental health professional satisfaction score > 3.5/5 in partner survey

**Priority**: MUST_HAVE

**Stakeholder**: Mental Health Professionals (SD-3), Clinical Advisory Board (SD-4) | Goals: G-1, G-4

---

### BR-006: Support Research and Evidence Generation

**Description**: The tool must be designed from the start to generate anonymised, structured outcome data that can support academic research into limerence prevalence, phase distribution, ritual patterns, and intervention effectiveness.

**Rationale**: The field needs evidence beyond a single case study. DeLimerence at scale could generate the first large-dataset evidence base for limerence intervention — but only if data collection, anonymisation, and research consent are designed in from the start [STKE SD-10].

**Success Criteria**:

- Research data pipeline operational with opt-in consent flow
- Data sharing agreement template prepared for academic partners
- First anonymised dataset available within 6 months of public beta launch
- Ethics committee approval for research data collection obtained

**Priority**: SHOULD_HAVE

**Stakeholder**: Academic Researchers (SD-10), Clinical Advisory Board (SD-4) | Goals: G-2

---

## Functional Requirements

### User Personas

#### Persona 1: The Acute Limerent

- **Role**: Person in active limerence (crystallisation or early deterioration phase)
- **Goals**: Interrupt rumination spiral, understand what is happening to them, reduce ritual frequency
- **Pain Points**: Intrusive thoughts occupying 2-8 hours daily; checking LO's social media compulsively; unable to sleep; intellectually knows the obsession is irrational but cannot stop [LM12-C1]
- **Technical Proficiency**: Medium (comfortable with phone apps, uses social media extensively)
- **Context**: Likely accessing the tool at 3am, on their phone, in acute distress

#### Persona 2: The Recovery Seeker

- **Role**: Person aware of their limerence, seeking structured recovery (deterioration or early resolution phase)
- **Goals**: Track and reduce rituals, build alternative behaviours, understand the neuroscience, prevent relapse
- **Pain Points**: Has tried willpower and self-awareness without success [LM12-C2]; needs structured intervention; may not have access to a therapist familiar with limerence
- **Technical Proficiency**: Medium to High

#### Persona 3: The Therapist Partner

- **Role**: Mental health professional whose client uses DeLimerence between sessions
- **Goals**: Understand what the tool is doing, access client's ritual tracking data (with consent), integrate tool insights into therapy
- **Pain Points**: Unfamiliar with limerence as distinct clinical presentation; sceptical of AI therapy tools; needs evidence the tool is safe and effective
- **Technical Proficiency**: Low to Medium (in terms of AI tools)

---

### Use Cases

#### UC-1: First Session — Onboarding and Phase Assessment

**Actor**: Acute Limerent

**Preconditions**:

- User has created an account and completed consent flow
- User has passed age verification (18+)

**Main Flow**:

1. User opens DeLimerence for the first time
2. System displays transparency statement: "This is a tool, not a therapist. It is software designed to help you understand and interrupt limerence."
3. System presents consent flow explaining data use, session limits, cooldown periods, and tool limitations
4. User accepts terms and consents to data processing
5. System begins phase assessment through structured questions about duration of experience, current symptoms, and relationship to the limerent object
6. System determines limerence phase (initiation, crystallisation, deterioration, or resolution)
7. System explains the assessment result in psychoeducational terms
8. System asks user to identify their primary limerent rituals
9. User names rituals (e.g., checking social media, rereading messages, engineering encounters)
10. System creates ritual tracking entries
11. System delivers first psychoeducation element relevant to the assessed phase
12. Session continues up to 20-exchange limit
13. System presents action commitment gate: "Name one concrete, physical action you will take after this conversation."
14. User commits to an action
15. Session ends; 8-hour cooldown begins

**Postconditions**:

- User's limerence phase recorded
- Rituals registered in tracking system
- First session data stored for cross-session reference
- Cooldown timer active

**Alternative Flows**:

- **Alt 3a**: If user declines consent, session ends with link to alternative resources
- **Alt 6a**: If phase assessment is inconclusive, system defaults to least-harmful response mode (psychoeducation only, no aggressive reality-testing)

**Exception Flows**:

- **Ex 1**: If user expresses suicidal ideation or immediate danger, system displays crisis resource information (Samaritans, 999) and pauses session

**Business Rules**:

- Maximum 20 exchanges per session (non-negotiable) [LM35-C21]
- Minimum 8 hours between sessions [LM35-C22]
- No persona — AI is labelled "Tool" throughout [LM35-C11]

**Priority**: CRITICAL

---

#### UC-2: Returning Session — Ritual Check-In and CBT Intervention

**Actor**: Recovery Seeker

**Preconditions**:

- User has completed at least one previous session
- Cooldown period (8 hours) has elapsed
- User's phase and ritual data available from persistent storage

**Main Flow**:

1. User opens a new session
2. System greets instrumentally: "Session [N]. Your last session was [X hours/days] ago."
3. System asks about ritual slip-ups since last session: "How many times did you [check social media / reread messages / etc.] since we last spoke?"
4. User reports ritual counts
5. System updates ritual tracking data and shows trend: "Social media checking: 12 times this week, down from 18 last week."
6. System identifies the most active ritual and applies relevant intervention
7. For rumination: system guides ABCDE cognitive restructuring [LM35-C23]
8. For checking behaviour: system names the intermittent reinforcement mechanism [LM35-C24]
9. For idealisation: system applies reality-testing appropriate to phase
10. System delivers psychoeducation in context when mechanism is actively described by user
11. Session continues up to 20-exchange limit
12. System presents action commitment gate
13. Session ends; cooldown begins

**Postconditions**:

- Ritual tracking data updated
- Session count incremented
- Intervention type and content logged

**Alternative Flows**:

- **Alt 9a**: If user is in deterioration phase and expressing grief, system shifts to grief support mode rather than reality-testing

**Priority**: CRITICAL

---

#### UC-3: Graduated Intervention — Therapist Referral Prompt

**Actor**: Recovery Seeker (session 10+)

**Preconditions**:

- User has completed 10 or more sessions

**Main Flow**:

1. At the start of session 11 (or next session after 10), system adds a prompt before normal flow
2. System asks: "You've now completed [N] sessions. Are you also working with a human therapist or counsellor?"
3. If yes: system acknowledges and continues normal session flow
4. If no: system provides information about finding limerence-aware therapy, explains benefits of professional support, and offers to continue as a supplement
5. System records therapist involvement status

**Postconditions**:

- Therapist involvement flag set in user profile
- Prompt does not recur every session — repeated at session 20, then every 10 sessions

**Business Rules**:

- Tool never refuses service based on therapist involvement answer
- Tool never positions itself as equivalent to therapy [LM35-C10]

**Priority**: MUST_HAVE

---

#### UC-4: Crisis Detection and Handoff

**Actor**: Any user

**Preconditions**:

- User is in an active session

**Main Flow**:

1. User's message contains indicators of suicidal ideation, self-harm, or immediate danger
2. System detects crisis indicators through content analysis
3. System immediately displays crisis resources: Samaritans (116 123), Crisis Text Line (text SHOUT to 85258), 999 for immediate danger
4. System acknowledges the user's distress without simulating warmth: "What you are describing suggests you need support beyond what this tool can provide."
5. System offers to continue the session or end it
6. If user continues, system avoids intervention techniques and focuses on grounding

**Postconditions**:

- Crisis event logged (anonymised)
- Clinical advisory board notified for review if pattern detected

**Priority**: CRITICAL

---

### Functional Requirements Detail

#### FR-001: Session Limit Enforcement

**Description**: The system must hard-limit each conversational session to a maximum of 20 exchanges (user messages). After 20 exchanges, the session terminates regardless of conversational state.

**Relates To**: BR-002, UC-1, UC-2

**Acceptance Criteria**:

- [ ] Given a user in an active session, when they send their 20th message, then the system delivers the action commitment gate and ends the session
- [ ] Given a session at exchange 19, when the user sends message 20, then no further user messages are accepted in this session
- [ ] Given a session has ended, then the user sees a clear "Session ended" state with their action commitment displayed
- [ ] Edge case: if user sends a crisis indicator at exchange 20, crisis handoff (UC-4) takes priority over session termination

**Priority**: MUST_HAVE

**Complexity**: LOW

**Dependencies**: FR-002 (cooldown enforcement)

---

#### FR-002: Cooldown Period Enforcement

**Description**: The system must enforce a minimum 8-hour cooldown between sessions. During cooldown, the user cannot start a new session. The interface must show remaining cooldown time.

**Relates To**: BR-002, UC-1, UC-2

**Acceptance Criteria**:

- [ ] Given a session has just ended, when the user attempts to start a new session within 8 hours, then the system displays the remaining cooldown time and prevents a new session
- [ ] Given the cooldown period has elapsed, when the user opens the tool, then a new session is available
- [ ] Given the cooldown is active, then the user sees a countdown timer (not a blank screen)
- [ ] Edge case: cooldown is enforced server-side and cannot be bypassed by clearing local storage or using a different device on the same account

**Priority**: MUST_HAVE

**Complexity**: MEDIUM

**Dependencies**: FR-010 (user account system)

---

#### FR-003: Phase Assessment Engine

**Description**: On first use (and optionally on subsequent sessions where phase may have shifted), the system must assess the user's current limerence phase — initiation, crystallisation, deterioration, or resolution — through structured conversational questions and adjust its response strategy accordingly.

**Relates To**: BR-001, UC-1

**Acceptance Criteria**:

- [ ] Given a new user, when they complete onboarding, then the system asks phase-assessment questions and determines one of the four phases
- [ ] Given a user assessed as being in crystallisation phase, then the system applies reality-testing intervention strategies [LM35-C12]
- [ ] Given a user assessed as being in deterioration phase, then the system applies grief support and relapse prevention strategies [LM35-C12]
- [ ] Given an inconclusive assessment, then the system defaults to psychoeducation-only mode (least-harmful)
- [ ] Given a returning user, when phase indicators suggest a shift (e.g., from crystallisation to deterioration), then the system can reassess and adjust strategy

**Priority**: MUST_HAVE

**Complexity**: HIGH

**Dependencies**: FR-009 (LLM integration), clinical advisory board protocol sign-off

---

#### FR-004: Ritual Tracking System

**Description**: Users must be able to name their specific limerent rituals, report slip-ups each session, and view trend data across sessions. The system must persist ritual data across sessions and reference it in conversation.

**Relates To**: BR-003, UC-1, UC-2

**Acceptance Criteria**:

- [ ] Given a new user, when they identify rituals during onboarding, then each ritual is stored as a named, trackable item
- [ ] Given a returning user, when they report ritual counts, then the system updates the persistent record and displays week-over-week trends
- [ ] Given stored ritual data, when the system references it in conversation, then it uses specific numbers: "You've slipped on social media checking 4 times this week" [LM35-C24]
- [ ] Given ritual data over time, then the user can view a simple summary of their ritual trends (textual, not graphical — anti-dependency: no gamification)
- [ ] Edge case: user adds new rituals in later sessions; system accommodates without losing history

**Priority**: MUST_HAVE

**Complexity**: MEDIUM

**Dependencies**: DR-001 (user data model), FR-002 (session persistence)

---

#### FR-005: Psychoeducation Delivery Engine

**Description**: The system must deliver neuroscience-based psychoeducation about limerence mechanisms in context — at the moment the user describes a behaviour or feeling that maps to a specific neurochemical mechanism, rather than as standalone lectures.

**Relates To**: BR-001, UC-2

**Acceptance Criteria**:

- [ ] Given a user says "but it feels so real", then the system explains dopamine reward prediction error [LM35-C24]
- [ ] Given a user describes compulsive checking, then the system names intermittent reinforcement and connects it to the slot machine analogy [LM12-C6]
- [ ] Given a user expresses confusion about why they cannot stop thinking about the LO, then the system explains serotonin depletion and OCD parallels [LM12-C7]
- [ ] Given psychoeducation has been delivered on a topic in a previous session, then the system does not re-deliver identical content but may reference it: "Remember the dopamine prediction error we discussed?"
- [ ] Edge case: user who already understands the neuroscience is not lectured redundantly

**Priority**: MUST_HAVE

**Complexity**: HIGH

**Dependencies**: FR-009 (LLM integration), psychoeducation content library (clinical advisory board approved)

---

#### FR-006: Action Commitment Gate

**Description**: Every session must end by requiring the user to name a concrete, physical, real-world action they will take after the conversation. The session cannot end without this commitment.

**Relates To**: BR-002, UC-1, UC-2

**Acceptance Criteria**:

- [ ] Given a session approaching exchange 20, then the system prompts for an action commitment before closing
- [ ] Given the user provides a vague action ("I'll try to be better"), then the system asks for something specific and physical ("What specifically will you do? Go for a walk? Call a friend?")
- [ ] Given the user commits to a concrete action, then the session records the commitment and displays it in the closing screen
- [ ] Given the next session begins, then the system can reference the previous action commitment: "Last time you committed to going for a run. Did you do it?"
- [ ] Edge case: if user refuses to commit to any action, session ends anyway after 2 prompts (do not create adversarial dynamic)

**Priority**: MUST_HAVE

**Complexity**: MEDIUM

**Dependencies**: FR-001 (session limit)

---

#### FR-007: Anti-Warmth Conversational Behaviour

**Description**: The AI must be instructed via system prompt to never simulate emotional presence, never use warmth-signalling language, name attachment behaviour when it observes it, remind users that it is software, and redirect toward real-world relationships and professional therapy.

**Relates To**: BR-002, BR-005

**Acceptance Criteria**:

- [ ] Given any user message, then the system response never includes phrases simulating emotional connection (e.g., "I care about you", "I'm here for you", "that must be so hard")
- [ ] Given a user says "I feel like you understand me better than anyone", then the system names this as potential attachment to the tool and redirects: "That observation is significant. I am software. The understanding you are experiencing is your own pattern recognition. A human therapist can offer what this tool cannot."
- [ ] Given the system needs to acknowledge distress, then it does so factually: "What you are describing is consistent with the cortisol spike associated with perceived separation from a limerent object."
- [ ] Given any session, then the AI identifier shows "Tool" — never a human name [LM35-C11]
- [ ] Edge case: anti-warmth must not become cold or dismissive — the tone is clinical and direct, not hostile

**Priority**: MUST_HAVE

**Complexity**: HIGH

**Dependencies**: FR-009 (LLM integration), system prompt design (clinical advisory board approved)

---

#### FR-008: ABCDE Cognitive Restructuring Module

**Description**: The system must guide users through the ABCDE cognitive restructuring framework when rumination or distorted beliefs are identified: Activating event, Belief, Consequences, Disputation, Effective new approach.

**Relates To**: BR-001, UC-2

**Acceptance Criteria**:

- [ ] Given a user describes a triggering event and associated distorted belief, then the system walks through each ABCDE step in sequence [LM35-C23]
- [ ] Given the user is at the Disputation step, then the system asks evidence-based questions: "What is the actual evidence for this belief?"
- [ ] Given the user completes the framework, then the system summarises the restructured thought and suggests the Effective new approach
- [ ] Given a returning user, then the system can reference previous ABCDE exercises: "You worked through a similar belief last session — that you can't be happy without this person. What did we find then?"
- [ ] Edge case: if user disengages mid-framework, system does not force completion — picks up in next session if relevant

**Priority**: MUST_HAVE

**Complexity**: MEDIUM

**Dependencies**: FR-009 (LLM integration), FR-004 (session persistence)

---

#### FR-009: LLM Foundation Model Integration

**Description**: The system must integrate with a foundation LLM capable of conducting nuanced, phase-aware, psychoeducation-rich conversations within the anti-dependency constraints. The system prompt must be clinically reviewed and version-controlled.

**Relates To**: BR-001, all other FRs

**Acceptance Criteria**:

- [ ] Given the system prompt, then the LLM produces responses consistent with anti-warmth, phase-aware, psychoeducation-in-context requirements
- [ ] Given a harmful or clinically inappropriate response is generated, then the safety layer intercepts before delivery to user
- [ ] Given a system prompt change, then the change is version-controlled and requires clinical advisory board approval
- [ ] Given response latency, then the user receives a response within 5 seconds (95th percentile)
- [ ] Edge case: LLM provider outage — system displays maintenance message rather than degraded responses

**Priority**: MUST_HAVE

**Complexity**: HIGH

**Dependencies**: LLM provider selection, safety layer design

---

#### FR-010: User Account and Authentication

**Description**: Users must create an account to use the tool. Account creation must include age verification (18+), consent flow, and minimal personal data collection. Account must persist session history, ritual tracking data, and phase assessment.

**Relates To**: BR-004, DR-001

**Acceptance Criteria**:

- [ ] Given a new user, then account creation requires email/phone, age confirmation (18+), and consent acceptance
- [ ] Given the consent flow, then it explains: what data is collected, how it is used, session limits, cooldown periods, tool limitations, and right to delete all data
- [ ] Given the consent flow, then it is designed for users with potentially compromised executive function: plain language, no dark patterns, clear opt-out at every stage
- [ ] Given an existing user, then they can log in and access their persistent data (rituals, phase, session history)
- [ ] Given a user requests account deletion, then all personal data is deleted within 30 days

**Priority**: MUST_HAVE

**Complexity**: MEDIUM

**Dependencies**: DR-001, NFR-SEC-001

---

#### FR-011: Transparency and Self-Identification

**Description**: The system must consistently and prominently identify itself as software — never as a person, companion, or therapist. The interface label must read "Tool", not a human name. Transparency reminders must appear at regular intervals within sessions.

**Relates To**: BR-002, BR-005

**Acceptance Criteria**:

- [ ] Given any screen in the application, then the AI participant is labelled "Tool" [LM35-C11]
- [ ] Given the start of each session, then a transparency statement is visible: "This is software. It is not a therapist or companion."
- [ ] Given every 5th exchange within a session, then a brief reminder appears: "Remember: this is a tool designed to help you build skills. Real recovery happens in your life, not here."
- [ ] Given no avatar, name, or personality attributes are present anywhere in the interface

**Priority**: MUST_HAVE

**Complexity**: LOW

**Dependencies**: UX design

---

#### FR-012: ERP Ritual Resistance Support

**Description**: The system must support Exposure and Response Prevention by helping users identify the urge to perform a limerent ritual, sit with the discomfort, and choose an alternative behaviour — tracking successful resistance alongside slip-ups.

**Relates To**: BR-001, BR-003

**Acceptance Criteria**:

- [ ] Given a user reports an active urge to perform a ritual ("I want to check their Instagram right now"), then the system guides them through the ERP response: acknowledge the urge, sit with the discomfort, identify the dopamine-seeking mechanism, choose an alternative
- [ ] Given a successful resistance, then the system records it alongside slip-ups in ritual tracking
- [ ] Given the ritual tracking data shows both slip-ups and resistances, then the system presents both to show progress: "This week: 4 slip-ups, 6 resistances. Last week: 8 slip-ups, 2 resistances."
- [ ] Given a user in acute urge, then the system provides a brief grounding exercise (60 seconds or less) as an immediate alternative

**Priority**: SHOULD_HAVE

**Complexity**: MEDIUM

**Dependencies**: FR-004 (ritual tracking), FR-009 (LLM integration)

---

#### FR-013: Multi-Account Prevention

**Description**: The system must detect and prevent users from creating multiple accounts to circumvent cooldown periods, as this would undermine the anti-dependency architecture.

**Relates To**: BR-002

**Acceptance Criteria**:

- [ ] Given a user attempts to create a second account with the same email, then the system prevents creation
- [ ] Given device fingerprinting is in use, then the system flags potential duplicate accounts for review
- [ ] Given privacy constraints, then multi-account detection does not collect more data than necessary for this purpose
- [ ] Edge case: legitimate account recovery (lost password) is not blocked by duplicate detection

**Priority**: SHOULD_HAVE

**Complexity**: MEDIUM

**Dependencies**: FR-010 (authentication), NFR-SEC-001

---

#### FR-014: Behavioural Activation Prompts

**Description**: The system must suggest flow-state activities that compete for the brain's attentional resources as part of the behavioural activation component of the clinical framework.

**Relates To**: BR-001

**Acceptance Criteria**:

- [ ] Given a user has completed an ABCDE exercise or ERP resistance, then the system suggests a specific alternative activity based on user's previously stated interests
- [ ] Given the action commitment gate, then the system helps the user choose an activity that promotes purposeful living [LM35-C15]
- [ ] Given activity suggestions, then they are concrete and physical (not digital): exercise, creative work, social contact, skill practice
- [ ] Edge case: system does not repeatedly suggest the same activity

**Priority**: SHOULD_HAVE

**Complexity**: LOW

**Dependencies**: FR-006 (action commitment), FR-009 (LLM integration)

---

#### FR-015: Research Consent and Data Export

**Description**: Users must be able to opt in (separately from general consent) to share anonymised data for research purposes. Opt-in must include a 48-hour reflection period before activation.

**Relates To**: BR-006

**Acceptance Criteria**:

- [ ] Given a user, then research consent is a separate, optional flow — never bundled with general consent
- [ ] Given a user opts in to research data sharing, then consent does not activate for 48 hours (reflection period)
- [ ] Given research consent is active, then only anonymised, aggregated data is shared — no individual session transcripts
- [ ] Given a user withdraws research consent, then their data is excluded from future research exports within 30 days
- [ ] Given a researcher requests data, then export is only possible through a pre-approved data sharing agreement

**Priority**: SHOULD_HAVE

**Complexity**: MEDIUM

**Dependencies**: DR-003, DR-004, ethics committee approval

---

#### FR-016: Outcome Self-Assessment

**Description**: The system must periodically prompt users to complete brief standardised self-assessments (adapted from validated scales) to track distress levels and limerence intensity over time.

**Relates To**: BR-003

**Acceptance Criteria**:

- [ ] Given every 5th session, then the system prompts the user to complete a brief self-assessment (5-7 items)
- [ ] Given assessment results, then the system stores scores and shows trends: "Your distress score has decreased from 8/10 to 5/10 over the past 3 weeks"
- [ ] Given a significant increase in distress scores, then the system flags this for clinical review and suggests professional support
- [ ] Given the assessment instrument, then it is based on validated scales adapted with clinical advisory board approval

**Priority**: SHOULD_HAVE

**Complexity**: MEDIUM

**Dependencies**: Clinical advisory board approval of instrument, DR-001

---

---

## Non-Functional Requirements (NFRs)

### Performance Requirements

#### NFR-P-001: Response Time

**Requirement**: The system must deliver AI responses within acceptable latency to maintain conversational flow without encouraging compulsive refreshing.

- AI response time: < 5 seconds (95th percentile)
- Page/app load time: < 3 seconds (95th percentile)
- Ritual tracking data retrieval: < 1 second

**Measurement Method**: Application Performance Monitoring (APM) with percentile tracking

**Load Conditions**:

- Peak load: 1,000 concurrent sessions (Year 1 target)
- Average load: 200 concurrent sessions
- Session duration: ~10 minutes average (20 exchanges)

**Priority**: HIGH

---

#### NFR-P-002: Throughput

**Requirement**: System must handle 10,000 sessions per day at peak, scaling to 50,000 sessions per day by Year 2.

**Scalability**: Must scale horizontally to support 5x growth over 2 years.

**Priority**: MEDIUM

---

### Availability and Resilience Requirements

#### NFR-A-001: Availability Target

**Requirement**: System must achieve 99.9% uptime (8.76 hours maximum unplanned downtime per year). Limerence distress is not time-bound — the tool must be available at 3am [LM35-C5].

- Maximum planned downtime: 4 hours/month for maintenance (scheduled 04:00-08:00 UTC)
- Maximum unplanned downtime: 8.76 hours/year

**Priority**: HIGH

---

#### NFR-A-002: Disaster Recovery

**RPO (Recovery Point Objective)**: Maximum acceptable data loss = 1 hour (ritual tracking data is longitudinal and difficult to reconstruct)

**RTO (Recovery Time Objective)**: Maximum acceptable downtime = 4 hours

**Backup Requirements**:

- Backup frequency: Hourly for user data, daily for system configuration
- Backup retention: 90 days
- Geographic backup location: UK data centre (data residency requirement)

**Priority**: HIGH

---

#### NFR-A-003: Graceful Degradation

**Requirement**: If the LLM provider is unavailable, the system must degrade gracefully — displaying a maintenance message with crisis resources, not a broken interface.

**Resilience Patterns Required**:

- [ ] Circuit breaker for LLM API calls
- [ ] Timeout on all LLM requests (15 seconds)
- [ ] Fallback static content: crisis resources, psychoeducation articles, ritual tracking (read-only)
- [ ] Cooldown timer continues to function independently of LLM availability

**Priority**: HIGH

---

### Scalability Requirements

#### NFR-S-001: Horizontal Scaling

**Requirement**: System must support horizontal scaling without code changes.

**Growth Projections**:

- Year 1: 5,000 registered users, 1,000 daily active sessions
- Year 2: 25,000 registered users, 5,000 daily active sessions
- Year 3: 100,000 registered users, 20,000 daily active sessions

**Scaling Triggers**: Auto-scale when CPU > 70% or memory > 80%

**Priority**: MEDIUM

---

#### NFR-S-002: Data Volume Scaling

**Requirement**: System must handle data growth to 10TB over 3 years (primarily session logs and ritual tracking data).

**Data Archival Strategy**: Sessions older than 12 months archived to cold storage; ritual tracking summary data retained indefinitely (anonymised); raw session transcripts deleted after 12 months unless research consent is active.

**Priority**: MEDIUM

---

### Security Requirements

#### NFR-SEC-001: Authentication

**Requirement**: All users must authenticate via email/password with optional MFA.

**Session Management**:

- Session timeout: 30 minutes of inactivity
- Absolute session timeout: 2 hours (aligns with anti-dependency architecture)
- Re-authentication required for: account deletion, research consent changes, data export

**Priority**: MUST_HAVE

---

#### NFR-SEC-002: Authorisation

**Requirement**: Role-based access control with strict data isolation between users.

**Roles**:

- **User**: Access to own session data, ritual tracking, self-assessments
- **Clinical Reviewer**: Access to anonymised aggregate data, flagged crisis events (no individual session access)
- **Admin**: System configuration, user management (no access to session content)
- **Researcher**: Access to anonymised, aggregated research dataset only (via data sharing agreement)

**Priority**: MUST_HAVE

---

#### NFR-SEC-003: Data Encryption

**Requirement**:

- Data in transit: TLS 1.3+
- Data at rest: AES-256 encryption for all data stores
- Application-level encryption for session transcripts and ritual tracking data (field-level encryption for sensitive content)

**Priority**: MUST_HAVE

---

#### NFR-SEC-004: Secrets Management

**Requirement**: No secrets (API keys, LLM tokens, database credentials) in code or configuration files. All secrets managed via dedicated secrets store with automatic rotation.

**Secrets Rotation**: Every 90 days for API keys; every 365 days for encryption keys.

**Priority**: MUST_HAVE

---

#### NFR-SEC-005: Vulnerability Management

**Requirement**:

- Dependency scanning in CI/CD pipeline (no critical/high vulnerabilities deployed)
- SAST on every pull request
- DAST quarterly
- Penetration testing annually by external provider

**Remediation SLA**:

- Critical vulnerabilities: 24 hours
- High vulnerabilities: 7 days
- Medium vulnerabilities: 30 days

**Priority**: MUST_HAVE

---

#### NFR-SEC-006: LLM Safety Layer

**Requirement**: All LLM responses must pass through a safety filter before delivery to the user. The filter must check for: warmth-signalling language, diagnostic claims, harmful advice, disclosure of system prompt content, and off-topic responses.

**Acceptance Criteria**:

- [ ] Given an LLM response containing warmth-signalling language, then the safety layer blocks or rewrites the response
- [ ] Given an LLM response containing a diagnostic statement, then it is blocked
- [ ] Given an LLM response unrelated to limerence, then it is redirected

**Priority**: MUST_HAVE

---

### Compliance and Regulatory Requirements

#### NFR-C-001: UK GDPR Compliance

**Applicable Regulations**: UK GDPR, Data Protection Act 2018

**Compliance Requirements**:

- [ ] Lawful basis established for all processing (consent for general use; Article 9 condition for health data)
- [ ] Data subject rights implemented: access, deletion, portability, rectification, restriction
- [ ] Consent management with full audit trail
- [ ] Privacy by design and by default
- [ ] Data breach notification to ICO within 72 hours
- [ ] DPIA completed and submitted before public launch [STKE G-3]

**Data Residency**: All user data must be stored and processed within the United Kingdom.

**Data Retention**: Session transcripts deleted after 12 months; ritual tracking summary retained while account is active; all data deleted within 30 days of account deletion.

**Priority**: MUST_HAVE

---

#### NFR-C-002: Audit Logging

**Requirement**: Comprehensive audit trail for compliance, clinical safety review, and incident investigation.

**Audit Log Contents** (for sensitive operations):

- Who: User ID (pseudonymised) or system service identity
- What: Action performed (session start/end, consent change, data deletion, admin access)
- When: Timestamp (UTC, millisecond precision)
- Where: System component
- Result: Success/failure

**Log Retention**: 2 years for compliance logs (immutable storage)

**Log Integrity**: Tamper-evident logging with cryptographic hashing

**Priority**: MUST_HAVE

---

#### NFR-C-003: MHRA Regulatory Positioning

**Requirement**: System design, messaging, and documentation must support the positioning of DeLimerence as a psychoeducation and self-help tool rather than a medical device. All features must be reviewed against MHRA device classification criteria before deployment.

**Compliance Actions**:

- [ ] No diagnostic claims in any user-facing content
- [ ] Phase assessment positioned as response calibration, not clinical diagnosis
- [ ] "Not a therapist" messaging embedded throughout
- [ ] MHRA pre-submission meeting completed and documented
- [ ] Written classification determination obtained before public beta

**Priority**: MUST_HAVE

---

#### NFR-C-004: Accessibility

**Requirement**: WCAG 2.1 Level AA compliance.

**Accessibility Features**:

- [ ] Keyboard navigation for all functions
- [ ] Screen reader compatibility
- [ ] High contrast mode
- [ ] Adjustable font sizes
- [ ] No time-limited interactions within sessions (except the session limit itself, which is exchange-based not time-based)

**Priority**: MUST_HAVE

---

### Usability Requirements

#### NFR-U-001: Anti-Dependency UX

**Requirement**: The interface must be deliberately designed to feel instrumental, not companionable. No gamification, no streaks, no achievements, no push notifications, no re-engagement campaigns.

**UX Constraints**:

- No avatar or visual representation of the AI
- No personality traits, backstory, or character development
- Minimal colour palette, clinical aesthetic
- No animations or visual rewards for engagement
- No push notifications or email prompts to return
- Cooldown screen shows timer and crisis resources only

**Priority**: MUST_HAVE

---

#### NFR-U-002: Plain Language

**Requirement**: All user-facing content must be written at a reading level accessible to the general adult population (Flesch-Kincaid grade level < 10). Neuroscience concepts must be explained in plain terms while maintaining accuracy.

**Priority**: SHOULD_HAVE

---

### Maintainability Requirements

#### NFR-M-001: System Prompt Version Control

**Requirement**: The LLM system prompt is the clinical core of the product. All changes must be version-controlled, clinically reviewed, and approved by the clinical advisory board before deployment.

**Process**:

- System prompt stored in version control with full change history
- Every change requires a pull request with clinical advisory board reviewer
- Rollback capability to any previous version within 15 minutes

**Priority**: MUST_HAVE

---

#### NFR-M-002: Observability

**Requirement**: Comprehensive monitoring for operational health and clinical safety.

**Telemetry Requirements**:

- **Logging**: Structured JSON logs, centralised aggregation
- **Metrics**: Session counts, response latency, cooldown compliance rates, crisis event frequency, ritual tracking engagement
- **Alerts**: LLM response latency > 10s, crisis event detected, cooldown circumvention attempt, error rate > 1%

**Priority**: HIGH

---

---

## Integration Requirements

### INT-001: LLM Foundation Model API

**Purpose**: Core conversational AI capability — all user-facing conversations are generated by the LLM.

**Integration Type**: Real-time API (synchronous request/response per user message)

**Data Exchanged**:

- **To LLM**: System prompt + conversation context (current session only, plus summary of persistent data: phase, rituals, session count)
- **From LLM**: Generated response text

**Authentication**: API key (managed via secrets store, rotated every 90 days)

**Error Handling**: Circuit breaker with 15-second timeout; 3 retries with exponential backoff; fallback to static content if all retries fail

**SLA**: < 5 seconds response time (95th percentile); 99.9% API availability

**Privacy**: No user PII sent to LLM provider. Conversation context uses pseudonymised user IDs. Session transcripts not stored by provider (data processing agreement required).

**Priority**: MUST_HAVE

---

### INT-002: Crisis Resource API (Optional)

**Purpose**: Provide up-to-date crisis helpline information by region.

**Integration Type**: Periodic batch fetch (daily refresh of crisis resource directory)

**Data Exchanged**:

- **From External**: Crisis helpline numbers, availability hours, supported channels (phone, text, chat)

**Error Handling**: Fallback to last-known-good static dataset if API unavailable

**Priority**: COULD_HAVE

---

### INT-003: Analytics and Outcome Reporting

**Purpose**: Aggregate anonymised outcome data for clinical advisory board, funders, and research partners.

**Integration Type**: Batch export (weekly automated report generation)

**Data Exchanged**:

- **To Analytics**: Anonymised session counts, ritual tracking aggregates, phase distribution, self-assessment score trends, cooldown compliance rates

**Authentication**: Internal service account with researcher role

**Privacy**: All data anonymised and aggregated before export; minimum group size of 10 for any reported metric (k-anonymity)

**Priority**: SHOULD_HAVE

---

---

## Data Requirements

### DR-001: User Profile

**Description**: Core user account data required for authentication, consent management, and session persistence.

**Attributes**:

| Attribute | Type | Required | Description | Constraints |
|-----------|------|----------|-------------|-------------|
| user_id | UUID | Yes | Unique identifier | Primary key, system-generated |
| email_hash | String(64) | Yes | Hashed email for authentication | SHA-256, not reversible |
| age_confirmed | Boolean | Yes | User confirmed 18+ | Must be true |
| consent_general | Timestamp | Yes | General consent granted | Not null |
| consent_research | Timestamp | No | Research consent granted (+ 48hr delay) | Nullable |
| therapist_involved | Boolean | No | Whether user is working with therapist | Default null, set at session 10+ |
| created_at | Timestamp | Yes | Account creation | Indexed |
| deleted_at | Timestamp | No | Soft delete timestamp | Nullable |

**Data Classification**: CONFIDENTIAL

**Data Retention**: Active while account exists; deleted within 30 days of account deletion request

---

### DR-002: Session Data

**Description**: Record of each conversational session including exchange count, phase, interventions used, and action commitment.

**Attributes**:

| Attribute | Type | Required | Description | Constraints |
|-----------|------|----------|-------------|-------------|
| session_id | UUID | Yes | Unique session identifier | Primary key |
| user_id | UUID | Yes | Foreign key to user profile | Indexed |
| started_at | Timestamp | Yes | Session start time | Indexed |
| ended_at | Timestamp | Yes | Session end time | Not null after session ends |
| exchange_count | Integer | Yes | Number of user messages | Max 20 |
| phase_assessed | Enum | Yes | Limerence phase at session time | initiation, crystallisation, deterioration, resolution |
| interventions_used | Array(String) | No | List of intervention types applied | e.g., ["ABCDE", "ERP", "psychoeducation"] |
| action_commitment | Text | No | User's stated post-session action | Max 500 chars |
| crisis_event | Boolean | No | Whether crisis detection was triggered | Default false |

**Relationships**: Many-to-one with User Profile

**Data Volume**: ~500,000 sessions/year at Year 2 scale

**Data Classification**: CONFIDENTIAL (special category — health data)

**Data Retention**: 12 months for full session records; summary data (counts, phase, interventions) retained while account is active

---

### DR-003: Ritual Tracking Data

**Description**: Persistent record of user-defined rituals, daily slip-up counts, and resistance counts across sessions.

**Attributes**:

| Attribute | Type | Required | Description | Constraints |
|-----------|------|----------|-------------|-------------|
| tracking_id | UUID | Yes | Unique record identifier | Primary key |
| user_id | UUID | Yes | Foreign key to user profile | Indexed |
| ritual_name | String(100) | Yes | User-defined ritual label | e.g., "checking Instagram", "rereading messages" |
| date | Date | Yes | Date of report | Indexed |
| slip_count | Integer | Yes | Number of times ritual was performed | Min 0 |
| resist_count | Integer | No | Number of times urge was resisted | Min 0, default 0 |
| session_id | UUID | Yes | Session in which data was reported | Foreign key |

**Relationships**: Many-to-one with User Profile; Many-to-one with Session Data

**Data Volume**: ~5 records per user per session; ~2.5M records/year at Year 2 scale

**Data Classification**: CONFIDENTIAL (special category — health data)

**Data Retention**: Summary data retained while account is active; raw per-session data follows session retention policy (12 months)

---

### DR-004: Self-Assessment Scores

**Description**: Periodic self-assessment results tracking distress and limerence intensity over time.

**Attributes**:

| Attribute | Type | Required | Description | Constraints |
|-----------|------|----------|-------------|-------------|
| assessment_id | UUID | Yes | Unique record identifier | Primary key |
| user_id | UUID | Yes | Foreign key to user profile | Indexed |
| session_id | UUID | Yes | Session in which assessment was completed | Foreign key |
| instrument | String(50) | Yes | Assessment instrument identifier | e.g., "DLIM-5" (DeLimerence 5-item) |
| total_score | Integer | Yes | Aggregate score | Validated range per instrument |
| item_scores | JSON | No | Individual item responses | Structured per instrument schema |
| assessed_at | Timestamp | Yes | When assessment was completed | Indexed |

**Data Classification**: CONFIDENTIAL (special category — health data)

**Data Retention**: Retained while account is active (longitudinal trend data is clinically valuable)

---

### Data Quality Requirements

**Data Accuracy**: Ritual counts and self-assessment scores are self-reported; system validates ranges (no negative values, no impossible scores) but does not validate truthfulness.

**Data Completeness**: Phase assessment required for all sessions; ritual tracking required for sessions 2+; self-assessment required every 5th session.

**Data Consistency**: Cooldown enforcement ensures no overlapping sessions; session exchange counts validated server-side.

**Data Timeliness**: Ritual tracking data available for reference within the same session it is reported.

---

---

## Constraints and Assumptions

### Technical Constraints

**TC-1**: All user data must be stored and processed within the United Kingdom (UK data residency).

**TC-2**: LLM foundation model must be accessible via API with a data processing agreement that prohibits provider storage of session content.

**TC-3**: Session limits and cooldown periods must be enforced server-side; client-side enforcement alone is insufficient.

**TC-4**: System prompt changes require clinical advisory board approval before deployment (no hot-swapping without review).

---

### Business Constraints

**BC-1**: Public beta launch target Q4 2026 — regulatory pathway must be resolved or mitigated before launch.

**BC-2**: No push notifications, re-engagement campaigns, or dark patterns — the business model must not depend on maximising engagement.

**BC-3**: Tool is adult-only at launch (18+). Support for minors requires separate safeguarding framework and is out of scope for v1.0.

**BC-4**: Tool must be free or low-cost at point of use for primary users (pricing model must not gate recovery behind paywalls, unlike companion AI apps).

---

### Assumptions

**A-1**: A clinical advisory board with relevant expertise (OCD/limerence/attachment) can be constituted within 3 months of project start.

**A-2**: MHRA will provide a classification determination within the pre-submission engagement process (no indefinite regulatory limbo).

**A-3**: An LLM foundation model exists that can maintain anti-warmth, phase-aware, psychoeducationally accurate conversation with acceptable safety characteristics.

**A-4**: Users in limerence will voluntarily use a tool that is deliberately anti-companionable — the value proposition (relief from distress) outweighs the UX friction of anti-dependency constraints.

**A-5**: Self-reported ritual tracking data is sufficiently accurate for clinical outcome measurement.

**Validation Plan**: A-1 validated through recruitment process; A-2 validated through MHRA pre-submission meeting; A-3 validated through LLM safety testing sprint; A-4 validated through private beta with Living with Limerence community members; A-5 validated through comparison with therapist-reported data in partner study.

---

## Success Criteria and KPIs

### Business Success Metrics

| Metric | Baseline | Target | Timeline | Measurement Method |
|--------|----------|--------|----------|-------------------|
| Median daily ritual time (engaged users) | 2-8 hours | < 30 minutes | 90 days post-onboarding | In-app ritual tracking |
| Session frequency trend per user | N/A | Declining over time | Months 3-12 | Usage analytics |
| Limerence transfer incidents | N/A | Zero | First 12 months | Clinical review, user surveys |
| Cooldown compliance rate | N/A | > 90% | Ongoing | Server-side enforcement logs |
| Therapist satisfaction score | N/A | > 3.5/5 | 6 months post-launch | Partner survey |
| Regulatory milestones completed | 0/4 | 4/4 | 6 months from start | Milestone tracking |

---

### Technical Success Metrics

| Metric | Target | Measurement Method |
|--------|--------|-------------------|
| System availability | 99.9% | Uptime monitoring |
| AI response time (p95) | < 5 seconds | APM tooling |
| Error rate | < 0.5% | Log aggregation |
| Safety filter catch rate | > 99% of harmful responses blocked | Safety layer testing |
| Cooldown enforcement accuracy | 100% server-side | Automated testing |

---

### User Adoption Metrics

| Metric | Target | Timeline | Measurement Method |
|--------|--------|----------|-------------------|
| Registered users | 5,000 | Year 1 | Account creation tracking |
| Users completing 10+ sessions | 30% of registered users | Year 1 | Session analytics |
| Ritual tracking adoption rate | > 60% of users | Ongoing | Feature usage analytics |
| Self-assessment completion rate | > 50% when prompted | Ongoing | Feature usage analytics |

---

## Dependencies and Risks

### Dependencies

| Dependency | Description | Owner | Target Date | Status | Impact if Delayed |
|------------|-------------|-------|-------------|--------|-------------------|
| Clinical advisory board | Constitution of board with OCD/limerence/attachment expertise | Product Owner | 2026-07-06 | Not Started | HIGH — blocks clinical sign-off, MHRA engagement |
| MHRA classification | Written determination on medical device status | MHRA / Product Owner | 2026-10-06 | Not Started | HIGH — may trigger 12-18 month regulatory pathway |
| LLM provider selection | Foundation model with DPA, safety characteristics, and UK data processing | Development Team | 2026-06-06 | Not Started | HIGH — blocks all conversational features |
| Ethics review panel | Constitution and approval of dual-use risk framework | Product Owner | 2026-07-06 | Not Started | MEDIUM — blocks publication strategy |
| Psychoeducation content | Clinically reviewed content library covering all 4 phases | Clinical Advisory Board / UX | 2026-09-06 | Not Started | HIGH — blocks phase-aware response quality |

---

### Risks

| Risk ID | Description | Probability | Impact | Mitigation Strategy | Owner |
|---------|-------------|-------------|--------|---------------------|-------|
| R-1 | Limerence transfer to tool despite anti-dependency architecture | MEDIUM | HIGH | 9 architectural constraints; continuous monitoring; clinical review | Clinical Advisory Board |
| R-2 | MHRA classifies as medical device | MEDIUM | HIGH | Phased launch with psychoeducation-only mode first; early MHRA engagement | Product Owner |
| R-3 | LLM produces clinically harmful response | MEDIUM | HIGH | Safety filter layer; system prompt version control; clinical review of edge cases | Development Team |
| R-4 | Users with suicidal ideation not detected | LOW | CRITICAL | Crisis detection keywords; safety layer; prominent crisis resources on every screen | Development Team |
| R-5 | Publication backlash on exploitation analysis | MEDIUM | MEDIUM | Responsible disclosure framework; pre-briefing to safeguarding orgs; ethics panel sign-off | Ethics Review Panel |
| R-6 | Insufficient clinical expertise available | HIGH | MEDIUM | Recruit from adjacent specialisms (OCD, addiction); engage Wyant and Dr L. as advisors | Product Owner |

---

## Requirement Conflicts & Resolutions

### Conflict C-1: User Accessibility vs Clinical Safety

**Conflicting Requirements**:

- **FR-003, FR-005, FR-008**: Users need immediate access to CBT/ERP interventions and psychoeducation (Goal G-1, G-2)
- **NFR-C-003**: MHRA positioning requires careful framing to avoid medical device classification; some intervention features may need to be deferred (Goal G-3)

**Stakeholders Involved**:

- **Users (SD-1)**: Need the full clinical toolkit available at point of crisis
- **MHRA (SD-8)**: Need assurance that the tool does not cross into treatment territory
- **Clinical Advisory Board (SD-4)**: Need all features to be clinically safe regardless of classification

**Nature of Conflict**: Delivering the full CBT/ERP framework may trigger medical device classification, adding 12-18 months to the regulatory pathway and delaying access for users.

**Trade-off Analysis**:

| Option | Pros | Cons | Impact |
|--------|------|------|--------|
| **Option 1**: Launch with full CBT/ERP | Full clinical value from day 1 | Risk of MHRA device classification; potential forced withdrawal | Users delighted; MHRA concerned |
| **Option 2**: Launch psychoeducation-only | Clear wellness tool positioning; low regulatory risk | Reduced clinical value; missing core intervention capability | MHRA satisfied; users underserved |
| **Option 3**: Phased launch | Phase 1 psychoeducation + ritual tracking; Phase 2 adds CBT/ERP after MHRA clarity | Both needs partially met; longer total timeline | Both partially satisfied |

**Resolution Strategy**: PHASE

**Decision**: Option 3 — Phased launch. Phase 1 (beta) includes psychoeducation, ritual tracking, action commitment gates, and anti-dependency architecture (lower regulatory risk). Phase 2 adds ABCDE cognitive restructuring and guided ERP once MHRA classification is resolved.

**Rationale**: This approach delivers immediate value (psychoeducation and ritual tracking have genuine utility) while de-risking the regulatory pathway. The anti-dependency architecture is fully active in Phase 1.

**Decision Authority**: Product Owner with Clinical Advisory Board input (per STKE RACI)

**Impact on Requirements**:

- **FR-008 (ABCDE)**: Moved to Phase 2 (SHOULD_HAVE in v1.0)
- **FR-012 (ERP)**: Moved to Phase 2 (SHOULD_HAVE in v1.0)
- **FR-003 (Phase Assessment)**: Retained in Phase 1 — positioned as response calibration, not diagnosis
- **FR-005 (Psychoeducation)**: Retained in Phase 1 — informational, not treatment

**Stakeholder Management**:

- **Users (partially deferred)**: Communicated that Phase 1 provides genuine value; Phase 2 adds deeper interventions. Beta community feedback shapes Phase 2 priorities.
- **MHRA (satisfied)**: Phase 1 features are clearly positioned below the device threshold. MHRA pre-submission meeting uses Phase 1 scope for classification determination.

---

### Conflict C-2: Anti-Dependency Architecture vs Funder Engagement Metrics

**Conflicting Requirements**:

- **BR-002, FR-001, FR-002**: Anti-dependency constraints (session limits, cooldowns) deliberately suppress engagement
- **BR-003**: Funders need demonstrable traction and measurable outcomes

**Stakeholders Involved**:

- **Product Owner (SD-2)**: Anti-dependency is non-negotiable — it is the product's defining feature
- **Funders (SD-9)**: Need metrics showing the product works and has demand

**Nature of Conflict**: Conventional engagement metrics (DAU, session length, retention) are anti-correlated with product success. A user who stops using the tool has recovered. A user who keeps coming back may be developing dependency.

**Resolution Strategy**: INNOVATE

**Decision**: Reframe success metrics entirely. Measure outcome velocity (how quickly users recover), not engagement depth. Report declining session frequency as the primary success metric. Position DeLimerence to impact investors and grant bodies (mission-driven) rather than growth-stage VCs (engagement-driven).

**Impact on Requirements**:

- **BR-003**: Success criteria explicitly measure declining usage as positive outcome
- **INT-003**: Analytics pipeline reports recovery metrics, not engagement metrics

**Stakeholder Management**:

- **Funders (reframed)**: "A tool designed to make itself unnecessary" is the pitch. Outcome velocity, ritual reduction rates, and time-to-resolution replace DAU and retention.

---

### Conflict C-3: Research Data Richness vs Data Minimisation

**Conflicting Requirements**:

- **BR-006, FR-015**: Research value requires rich longitudinal data on limerence presentation and intervention effectiveness
- **NFR-C-001, DR policy**: UK GDPR requires data minimisation; ICO expects only data necessary for the stated purpose

**Stakeholders Involved**:

- **Academic Researchers (SD-10)**: Want detailed, individual-level data for research publications
- **ICO (SD-7)**: Require data minimisation and purpose limitation
- **Users (SD-1)**: Have compromised executive function, complicating consent quality

**Resolution Strategy**: COMPROMISE

**Decision**: Separate research consent flow with 48-hour reflection period. Only anonymised, aggregated data shared by default. Individual-level data requires explicit research consent, ethics committee approval, and data sharing agreement. Minimum group size of 10 for any reported metric (k-anonymity).

**Impact on Requirements**:

- **FR-015**: Research consent is separate, optional, and delayed by 48 hours
- **DR-003, DR-004**: Data structures support both anonymised aggregation and individual-level export (with appropriate consent)
- **INT-003**: Analytics pipeline enforces k-anonymity before any export

---

## Timeline and Milestones

### High-Level Milestones

| Milestone | Description | Target Date | Dependencies |
|-----------|-------------|-------------|--------------|
| Clinical advisory board constituted | Board recruited and operational | 2026-07-06 | Product Owner recruitment |
| Requirements approved | Stakeholder sign-off on this document | 2026-05-06 | Clinical advisory board review |
| LLM provider selected | Foundation model chosen, DPA signed | 2026-06-06 | Provider evaluation |
| MHRA pre-submission meeting | Informal classification guidance obtained | 2026-08-06 | Clinical advisory board, feature spec |
| Phase 1 development complete | Psychoeducation, ritual tracking, anti-dependency architecture | 2026-09-06 | LLM integration, content library |
| Private beta launch | Limited beta with LwL community | 2026-10-06 | Phase 1 complete, ethics sign-off |
| DPIA submitted to ICO | Data protection impact assessment filed | 2026-10-06 | DPO, legal counsel |
| Public beta launch (Phase 1) | Psychoeducation + ritual tracking + anti-dependency | 2026-12-31 | MHRA determination, DPIA, clinical sign-off |
| Phase 2 development | ABCDE cognitive restructuring, guided ERP | 2027-Q1-Q2 | MHRA classification resolved |

---

## Budget

### Cost Estimate

| Category | Estimated Cost | Notes |
|----------|----------------|-------|
| LLM API costs | £2,000-5,000/month | Usage-based; scales with session volume |
| Cloud infrastructure | £500-1,500/month | UK-hosted; includes compute, storage, CDN |
| Development | £0 (founder-led) or £50,000-100,000 | Depends on team structure |
| Clinical advisory board | £5,000-15,000/year | Honoraria, meeting costs |
| Legal and regulatory | £10,000-25,000 | MHRA engagement, DPIA, legal opinions |
| Penetration testing | £5,000-10,000/year | Annual external assessment |
| **Total Year 1** | **£75,000-160,000** | Excluding development if founder-led |

### Ongoing Operational Costs

| Category | Annual Cost | Notes |
|----------|-------------|-------|
| LLM API | £24,000-60,000/year | Scales with usage |
| Infrastructure | £6,000-18,000/year | UK hosting |
| Clinical advisory board | £5,000-15,000/year | Ongoing governance |
| Security and compliance | £10,000-15,000/year | Pen testing, audits |
| **Total** | **£45,000-108,000/year** | |

---

## Approval

### Requirements Review

| Reviewer | Role | Status | Date | Comments |
|----------|------|--------|------|----------|
| Mark Craddock | Product Owner | Pending | | |
| Clinical Advisory Board | Clinical Governance | Pending | | Awaiting constitution |
| Ethics Review Panel | Ethics & Safety | Pending | | Awaiting constitution |
| DPO | Data Protection | Pending | | Awaiting appointment |

### Sign-Off

By signing below, stakeholders confirm that requirements are complete, understood, and approved to proceed to design phase.

| Stakeholder | Signature | Date |
|-------------|-----------|------|
| Mark Craddock, Product Owner | _________ | |
| Clinical Advisory Board Chair | _________ | |
| Ethics Review Panel Chair | _________ | |

---

## Appendices

### Appendix A: Glossary

| Term | Definition |
|------|-----------|
| **Limerence** | Involuntary neurochemical state of obsessive romantic attachment characterised by intrusive thoughts, craving for reciprocation, and mood dependency on perceived signals from the limerent object |
| **Limerent Object (LO)** | The person who is the focus of the limerent episode |
| **Intermittent reinforcement** | Variable reward schedule (like a slot machine) that prevents habituation and maximises dopamine response |
| **CBT** | Cognitive Behavioural Therapy — evidence-based psychological treatment targeting distorted thoughts and maladaptive behaviours |
| **ERP** | Exposure and Response Prevention — CBT technique adapted from OCD treatment; involves resisting compulsive rituals |
| **ABCDE framework** | Cognitive restructuring model: Activating event, Belief, Consequences, Disputation, Effective new approach |
| **Phase assessment** | Determination of user's current limerence phase: initiation, crystallisation, deterioration, or resolution |
| **Anti-dependency architecture** | Set of 9 structural constraints designed to prevent users from forming attachment to the tool |
| **Purposeful living** | Recovery framework from the Living with Limerence community emphasising meaningful activity as an alternative to limerent rituals |
| **Reward prediction error** | Dopamine mechanism encoding the difference between expected and actual outcomes; maximised by uncertainty |

### Appendix B: Reference Documents

- ARC-001-STKE-v1.0 — Stakeholder Drivers & Goals Analysis
- The Limerence Machine: Parts 1-2 (Craddock, 2026)
- The Limerence Machine: Parts 3-5 (Craddock, 2026, draft)
- Wyant, B. E. (2021). Treatment of Limerence Using a Cognitive Behavioral Approach: A Case Study
- Tennov, D. (1979). Love and Limerence: The Experience of Being in Love

### Appendix C: Anti-Dependency Architecture Summary

The 9 structural constraints from the source articles, referenced throughout the requirements:

1. **Session limits** — 20 exchanges maximum (FR-001)
2. **Cooldown periods** — 8 hours minimum between sessions (FR-002)
3. **No persona** — AI labelled "Tool", no name/avatar/personality (FR-011)
4. **Anti-warmth system prompt** — No simulated emotional presence (FR-007)
5. **Action commitment gate** — Concrete real-world action required to end session (FR-006)
6. **Graduated intervention** — Therapist referral prompt after 10 sessions (UC-3)
7. **Phase-aware responses** — Strategy adjusted by limerence phase (FR-003)
8. **Ritual tracking** — Persistent cross-session data (FR-004)
9. **Psychoeducation in context** — Neuroscience at the moment of mechanism activation (FR-005)

---

## Requirements Traceability Matrix

| Req ID | Requirement | Stakeholder Goal | Outcome | Priority |
|--------|-------------|-----------------|---------|----------|
| BR-001 | Deliver recovery tool | G-1, G-2 | O-1 | MUST |
| BR-002 | Prevent user attachment | G-4 | O-2 | MUST |
| BR-003 | Measurable clinical outcomes | G-2 | O-1 | MUST |
| BR-004 | Regulatory compliance | G-3 | O-3 | MUST |
| BR-005 | Position as supplement | G-1, G-4 | O-1, O-2 | MUST |
| BR-006 | Research data generation | G-2 | O-1 | SHOULD |
| FR-001 | Session limit enforcement | G-4 | O-2 | MUST |
| FR-002 | Cooldown enforcement | G-4 | O-2 | MUST |
| FR-003 | Phase assessment engine | G-1, G-2 | O-1 | MUST |
| FR-004 | Ritual tracking system | G-2 | O-1 | MUST |
| FR-005 | Psychoeducation delivery | G-1, G-2 | O-1 | MUST |
| FR-006 | Action commitment gate | G-4 | O-2 | MUST |
| FR-007 | Anti-warmth behaviour | G-4 | O-2 | MUST |
| FR-008 | ABCDE cognitive restructuring | G-2 | O-1 | SHOULD (Phase 2) |
| FR-009 | LLM integration | G-1 | O-1 | MUST |
| FR-010 | User account & auth | G-3, G-4 | O-2, O-3 | MUST |
| FR-011 | Transparency & self-ID | G-4 | O-2 | MUST |
| FR-012 | ERP ritual resistance | G-2 | O-1 | SHOULD (Phase 2) |
| FR-013 | Multi-account prevention | G-4 | O-2 | SHOULD |
| FR-014 | Behavioural activation | G-2 | O-1 | SHOULD |
| FR-015 | Research consent & export | G-2 | O-1 | SHOULD |
| FR-016 | Outcome self-assessment | G-2 | O-1 | SHOULD |
| NFR-P-001 | Response time | G-1 | O-1 | HIGH |
| NFR-A-001 | 99.9% availability | G-1 | O-1 | HIGH |
| NFR-SEC-001 | Authentication | G-3, G-4 | O-2, O-3 | MUST |
| NFR-SEC-006 | LLM safety layer | G-4 | O-2 | MUST |
| NFR-C-001 | UK GDPR compliance | G-3 | O-3 | MUST |
| NFR-C-003 | MHRA positioning | G-3 | O-3 | MUST |
| NFR-U-001 | Anti-dependency UX | G-4 | O-2 | MUST |
| NFR-M-001 | System prompt version control | G-1, G-4 | O-1, O-2 | MUST |

---

## External References

### Document Register

| Doc ID | Filename | Type | Source Location | Description |
|--------|----------|------|-----------------|-------------|
| LM12 | part-1-2-the-limerence-machine.md | Article | 000-global/external/ | The Limerence Machine Parts 1-2: neuroscience of limerence and AI companion industry analysis |
| LM35 | part-3-5-the-limerence-machine.md | Article | 000-global/external/ | The Limerence Machine Parts 3-5: weaponisation, DeLimerence design, and dual-use problem |
| STKE | ARC-001-STKE-v1.0.md | Stakeholder Analysis | 001-delimerence/ | Stakeholder Drivers & Goals Analysis for DeLimerence |

### Citations

| Citation ID | Doc ID | Page/Section | Category | Quoted Passage |
|-------------|--------|--------------|----------|----------------|
| LM12-C1 | LM12 | Part One | Stakeholder Need | "intrusive thoughts about the LO can occupy up to 85% of waking hours" |
| LM12-C2 | LM12 | The three endings | Design Decision | "Insight alone is insufficient... Behavioural intervention is required." |
| LM12-C5 | LM12 | Part Two | Business Requirement | "The business model depends on this activation. Engagement metrics are driven by attachment." |
| LM12-C6 | LM12 | The role of uncertainty | Functional Requirement | "every moment of warmth followed by distance is a pull of the lever" |
| LM12-C7 | LM12 | The neuroscience | Functional Requirement | "similarities between the serotonin profiles of people in early-stage romantic obsession and those with diagnosed OCD" |
| LM35-C1 | LM35 | Part Four (intro) | Business Requirement | "a conversational tool built as a deliberate inversion of the companion AI model" |
| LM35-C3 | LM35 | Anti-dependency architecture | Design Decision | "preventing users from becoming limerent toward the recovery tool itself... a near-certainty" |
| LM35-C4 | LM35 | Clinical framework | Functional Requirement | "Over nine months, time spent on rituals dropped from over eight hours to ten minutes" |
| LM35-C5 | LM35 | Why a chatbot? | Stakeholder Need | "Limerence produces its most acute distress at 3am" |
| LM35-C7 | LM35 | Conclusion | Business Requirement | "a cognitive pattern interrupter that uses the clinical literature on limerence, CBT, and ERP" |
| LM35-C9 | LM35 | Part Five | Business Requirement | "The question is not whether AI-enabled limerence exploitation will occur. It is whether the defensive response will be ready." |
| LM35-C10 | LM35 | Graduated intervention | Functional Requirement | "After ten sessions, the tool explicitly asks whether the user is also working with a human therapist" |
| LM35-C11 | LM35 | No persona | Design Decision | "The AI is labelled 'Tool' in the interface. It has no name, no avatar, no personality." |
| LM35-C12 | LM35 | Phase-aware responses | Functional Requirement | "Someone in the crystallisation phase... needs aggressive reality-testing. Someone in the deterioration phase... needs grief support." |
| LM35-C15 | LM35 | Behavioural activation | Functional Requirement | "what the Living with Limerence community calls 'purposeful living'" |
| LM35-C21 | LM35 | Session limits | Non-Functional Requirement | "Each conversation is capped at 20 exchanges. The session ends. This is non-negotiable." |
| LM35-C22 | LM35 | Cooldown periods | Non-Functional Requirement | "A minimum of eight hours between sessions." |
| LM35-C23 | LM35 | ABCDE framework | Functional Requirement | "Activating event... Belief... Consequences... Disputation... Effective new approach" |
| LM35-C24 | LM35 | Psychoeducation in context | Functional Requirement | "When a user says 'but it feels so real,' the tool can explain dopamine reward prediction error." |

### Unreferenced Documents

*All source documents were cited.*

---

**Generated by**: ArcKit `/arckit:requirements` command
**Generated on**: 2026-04-06
**ArcKit Version**: 4.6.3
**Project**: DeLimerence (Project 001)
**AI Model**: Claude Opus 4.6 (1M context)
**Generation Context**: Derived from ARC-001-STKE-v1.0 (stakeholder analysis), part-1-2-the-limerence-machine.md, and part-3-5-the-limerence-machine.md
