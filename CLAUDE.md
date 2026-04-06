# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

DeLimerence is an anti-dependency conversational AI tool for limerence recovery. It is the deliberate inversion of AI companion apps — designed to loosen attachment, not deepen it. The repository contains architecture governance artifacts (not application code). Implementation has not started.

## Repository Structure

This is an **ArcKit-governed architecture project**, not a codebase. All content is Markdown governance artifacts.

```
projects/
  000-global/              # Cross-project artifacts (principles)
    ARC-000-PRIN-v1.0.md   # 14 enterprise architecture principles
    external/              # Source articles (The Limerence Machine)
  001-delimerence/         # Main project
    ARC-001-{TYPE}-v*.md   # Governance artifacts (REQ, RISK, STKE, TRAC, ANAL, DPIA, SOBC, PRIN-COMP)
    decisions/             # 8 ADRs (ADR-001 through ADR-008)
    research/              # Technology research (v1.0) and grants research (v2.0)
    vendors/               # Vendor profiles (Anthropic, AWS, Supabase)
    tech-notes/            # Technical deep-dives
    external/              # External reference documents
docs/
  index.html               # Documentation site (GitHub Pages)
  manifest.json            # Document index for site
  health.json              # Governance health scan results
  guides/                  # ArcKit command guides
```

## ArcKit Plugin

The ArcKit plugin is configured in `.claude/settings.json`. It provides `/arckit:*` slash commands for generating governance artifacts. Run `/arckit:health` to check artifact health. Run `/arckit:pages` to regenerate the documentation site after changes.

## Document Naming Convention

All artifacts follow: `ARC-{PROJECT_ID}-{TYPE}-v{VERSION}.md`

- Project 000 = global (principles, policies)
- Project 001 = DeLimerence
- Types: REQ, RISK, STKE, TRAC, ANAL, DPIA, SOBC, PRIN-COMP, ADR, RSCH, PRIN

## Key Architecture Decisions

- **LLM**: Anthropic Claude via AWS Bedrock (eu-west-2, UK data residency)
- **Safety**: NeMo Guardrails + custom clinical warmth/diagnostic filters
- **Auth + DB**: Supabase (PostgreSQL with Row Level Security)
- **Infrastructure**: AWS Fargate, Next.js PWA
- **Regulatory**: Phased launch — Phase 1 psychoeducation only, Phase 2 CBT/ERP after MHRA clarity

## Anti-Dependency Architecture (Core Concept)

The 9 structural constraints are the product's defining feature and existential requirement. All must be enforced server-side:

1. Session limits (20 exchanges)
2. Cooldown periods (8 hours)
3. No persona (AI = "Tool")
4. Anti-warmth system prompt
5. Action commitment gate
6. Graduated intervention (therapist referral at session 10+)
7. Phase-aware responses (initiation/crystallisation/deterioration/resolution)
8. Ritual tracking (persistent cross-session)
9. Psychoeducation in context

## Domain Context

- **Limerence**: Involuntary neurochemical obsessive attachment (dopamine flooding, serotonin depletion, norepinephrine surges)
- **Clinical basis**: Single published case study (Wyant, 2021) using CBT/ERP adapted from OCD protocols
- **Dual-use concern**: Same knowledge enables both recovery tools and exploitation — responsible disclosure framing required
- **Users**: Psychologically vulnerable with potentially compromised executive function — consent and safety architecture must account for this
- **Data**: Special category health data under UK GDPR Article 9
