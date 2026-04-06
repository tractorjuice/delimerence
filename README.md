# DeLimerence

**How obsessive attachment is weaponised by AI Companion Apps at scale and the case for building the antidote**

DeLimerence is a conversational AI tool built as a deliberate inversion of the companion AI model. Where AI companion apps (Replika, Character.ai) deepen emotional attachment through intermittent reinforcement and simulated emotional presence, DeLimerence systematically loosens attachment using CBT, ERP, and psychoeducation grounded in the clinical literature on limerence.

## What is Limerence?

Limerence is an involuntary neurochemical state of obsessive romantic attachment characterised by intrusive thoughts (up to 85% of waking hours), craving for reciprocation, and mood dependency on perceived signals from the limerent object. It is not a crush or infatuation -- it is a distinct neurochemical state involving dopamine flooding, serotonin depletion (similar to OCD), norepinephrine surges, and cortisol spikes.

Anyone can experience it, regardless of intelligence, emotional maturity, or attachment history.

## The Problem

AI companion technology is already inducing limerence-like states at scale. The same mechanisms that make those products addictive also make them exploitable by criminal actors for sextortion, romance fraud, and child sexual exploitation. The exploitation pipeline documented in this project requires no novel technology -- only the integration of published neuroscience with commodity infrastructure (LLMs, social media, cryptocurrency).

## The Anti-Dependency Architecture

DeLimerence addresses this through 9 structural constraints enforced at infrastructure level:

1. **Session limits** -- 20 exchanges maximum per session
2. **Cooldown periods** -- 8 hours minimum between sessions
3. **No persona** -- AI labelled "Tool", no name, avatar, or personality
4. **Anti-warmth system prompt** -- no simulated emotional presence
5. **Action commitment gate** -- concrete real-world action required to end each session
6. **Graduated intervention** -- therapist referral prompt after 10 sessions
7. **Phase-aware responses** -- strategy adjusted by limerence phase
8. **Ritual tracking** -- persistent cross-session data on limerent behaviours
9. **Psychoeducation in context** -- neuroscience delivered at the moment of mechanism activation

## Architecture Governance

This repository contains the complete architecture governance for DeLimerence, built with [ArcKit](https://github.com/tractorjuice/arc-kit).

### Artifacts

| Category | Artifacts |
|----------|-----------|
| **Discovery** | Requirements (50 reqs), Stakeholder Analysis (12+ stakeholders), Research (technology + grants) |
| **Planning** | Strategic Outline Business Case (Green Book 5-case model) |
| **Architecture** | 14 Enterprise Principles, 8 Architecture Decision Records |
| **Governance** | Risk Register (15 risks), Traceability Matrix (76% coverage), Governance Analysis, Principles Compliance |
| **Compliance** | DPIA (10 privacy risks, UK GDPR Article 35) |

### Key Decisions

| ADR | Decision |
|-----|----------|
| ADR-001 | Use Anthropic Claude via AWS Bedrock for LLM |
| ADR-002 | Server-side anti-dependency enforcement |
| ADR-003 | Defence-in-depth safety layer (NeMo Guardrails + custom) |
| ADR-004 | Phased launch for MHRA regulatory de-risking |
| ADR-005 | Supabase Auth for authentication |
| ADR-006 | Supabase PostgreSQL with Row Level Security |
| ADR-007 | LLM-driven phase assessment with structured output |
| ADR-008 | Next.js PWA on AWS Fargate (eu-west-2) |

### Technology Stack

- **LLM**: Anthropic Claude (via AWS Bedrock, eu-west-2)
- **Safety Layer**: NVIDIA NeMo Guardrails + custom clinical filters
- **Auth + Database**: Supabase (Auth + PostgreSQL with RLS)
- **Infrastructure**: AWS Fargate, eu-west-2 (London)
- **Frontend**: Next.js Progressive Web App
- **Data Residency**: All data stored and processed within the UK

## Documentation Site

Browse all governance artifacts at the documentation site:

**GitHub Pages**: Enable in repository Settings > Pages > Source "Deploy from branch" > Branch "main", folder "/docs"

The site includes a governance dashboard, document viewer with Mermaid diagram rendering, and dependency graph visualisation.

## Clinical Framework

Based on the only published clinical case study on limerence treatment (Wyant, 2021), which used CBT techniques adapted from OCD protocols:

- **Exposure and Response Prevention (ERP)** -- resisting compulsive limerent rituals
- **ABCDE Cognitive Restructuring** -- challenging distorted beliefs about the limerent object
- **Behavioural Activation** -- redirecting energy toward purposeful living

## Regulatory Strategy

DeLimerence adopts a phased launch strategy to de-risk MHRA medical device classification:

- **Phase 1** (Beta): Psychoeducation + ritual tracking + anti-dependency architecture
- **Phase 2**: ABCDE cognitive restructuring + guided ERP (after MHRA classification resolved)

The MHRA/NICE AI Airlock (regulatory sandbox) is being explored as the regulatory pathway.

## Project Status

- **Phase**: Discovery/Alpha (governance complete, implementation not started)
- **Target**: Public beta Q4 2026
- **Funding Strategy**: Grant-funded with academic partner (AISI, Innovate UK, BGV)
- **Estimated 3-year cost**: £338,468
- **Governance Health**: All clear -- 0 findings across 7 detection rules

## References

- Tennov, D. (1979). *Love and Limerence: The Experience of Being in Love.* Scarborough House.
- Wyant, B. E. (2021). Treatment of Limerence Using a Cognitive Behavioral Approach: A Case Study. *Journal of Patient Experience, 8*, 1--7.
- Fisher, H., Aron, A., & Brown, L. L. (2005). Romantic love: An fMRI study of a neural mechanism for mate choice. *Journal of Comparative Neurology, 493*(1), 58--62.

## License

Apache License 2.0 -- see [LICENSE](LICENSE).
