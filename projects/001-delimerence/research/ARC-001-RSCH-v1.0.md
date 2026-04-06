# Technology and Service Research: DeLimerence

> **Template Origin**: Official | **ArcKit Version**: 4.6.3 | **Command**: `/arckit:research`

## Document Control

| Field | Value |
|-------|-------|
| **Document ID** | ARC-001-RSCH-v1.0 |
| **Document Type** | Technology and Service Research |
| **Project** | DeLimerence (Project 001) |
| **Classification** | OFFICIAL |
| **Status** | DRAFT |
| **Version** | 1.0 |
| **Created Date** | 2026-04-06 |
| **Last Modified** | 2026-04-06 |
| **Review Cycle** | Quarterly |
| **Next Review Date** | 2026-07-06 |
| **Owner** | Mark Craddock, Product Owner |
| **Reviewed By** | PENDING |
| **Approved By** | PENDING |
| **Distribution** | Project team, Clinical Advisory Board, Ethics Review Panel |

## Revision History

| Version | Date | Author | Changes | Approved By | Approval Date |
|---------|------|--------|---------|-------------|---------------|
| 1.0 | 2026-04-06 | ArcKit AI | Initial creation from `/arckit:research` command | PENDING | PENDING |

---

## Executive Summary

### Research Scope

This document presents research findings for technology, services, and products that can meet the requirements documented in `ARC-001-REQ-v1.0.md`. It provides build vs buy analysis and vendor recommendations for procurement decisions supporting the DeLimerence conversational AI tool -- an anti-dependency limerence recovery application using CBT/ERP techniques and psychoeducation.

**Requirements Analyzed**: 16 functional, 16 non-functional, 3 integration, 4 data requirements

**Research Categories Identified**: 7 categories based on requirement analysis

**Research Approach**: Market research via vendor websites and pricing pages, G2/Gartner review analysis, open source project assessment (GitHub), UK MHRA regulatory landscape review, and UK government code reuse search (govreposcrape)

### Key Findings

- **LLM Foundation Model**: Anthropic Claude (via AWS Bedrock for UK data residency) is the strongest fit given the need for nuanced, safety-aware conversation and a zero-data-retention DPA. Estimated cost of GBP 800-2,400/month at Year 1 scale.
- **LLM Safety Layer**: NVIDIA NeMo Guardrails (open source, Apache 2.0) combined with a custom clinical safety filter is recommended. No off-the-shelf product addresses the unique anti-warmth and clinical safety requirements.
- **Cloud Infrastructure**: AWS UK (eu-west-2, London) provides the best combination of UK data residency, managed services breadth, Bedrock integration, and healthcare/compliance tooling.
- **Authentication**: Supabase Auth is recommended for the combined authentication + database need, offering 50,000 free MAUs, GDPR compliance, and PostgreSQL bundled at GBP 25/month (Pro tier).
- **Application Framework**: Next.js (PWA) deployed via containerised hosting on AWS is recommended over native mobile development, reducing cost and time to market while meeting the anti-dependency UX requirements.

### Build vs Buy Summary

| Approach | Categories | Total 3-Year TCO | Rationale |
|----------|-----------|------------------|-----------|
| **BUILD** (Custom Development) | 3 categories (Safety Layer, Phase Assessment Engine, Anti-Dependency UX) | GBP 198,000 | Core IP; no off-the-shelf product exists for anti-warmth clinical AI |
| **BUY** (Commercial SaaS) | 2 categories (LLM API, Observability) | GBP 87,000 | Mature, cost-effective managed services |
| **ADOPT** (Open Source) | 2 categories (NeMo Guardrails framework, Supabase Auth+DB) | GBP 14,400 | Strong community, low cost, avoids lock-in |
| **GOV.UK Platforms** | 0 categories | GBP 0 | Not a UK Government service; GOV.UK platforms not applicable |
| **TOTAL** | 7 categories | **GBP 299,400** | Blended approach |

### Top Recommended Vendors

**Shortlist for further evaluation**:

1. **Anthropic Claude (via AWS Bedrock)** for LLM Foundation Model: Best-in-class safety training, nuanced conversational ability, UK data residency via Bedrock eu-west-2, zero-retention DPA available
2. **Supabase** for Authentication + Database: Combined auth and PostgreSQL at startup-friendly pricing, GDPR compliant, SOC 2 Type 2, encryption at rest and in transit
3. **AWS (eu-west-2 London)** for Cloud Infrastructure: UK data residency, broadest managed service catalogue, Bedrock integration, healthcare compliance tooling, Fargate serverless containers

### Requirements Coverage

- 95% of requirements have identified solutions (37 of 39)
- 2 requirements need custom development (no suitable off-the-shelf): FR-003 (Phase Assessment Engine), NFR-SEC-006 (Clinical Safety Layer)
- 0 requirements need further research

---

## Research Categories

> **Note**: Research categories were dynamically identified from DeLimerence requirements. Keywords scanned: "LLM", "conversation", "session", "authentication", "consent", "encryption", "data", "persistent storage", "ritual tracking", "monitoring", "audit", "secrets", "API key", "mobile", "web", "WCAG", "cooldown".

---

## Category 1: LLM Foundation Model Provider

**Requirements Addressed**: FR-009, INT-001, FR-003, FR-005, FR-007, FR-008, NFR-P-001, NFR-A-003, NFR-SEC-006

**Why This Category**: The entire conversational AI capability depends on an LLM that can conduct nuanced, phase-aware, psychoeducation-rich conversations within the anti-dependency constraints. This is the most critical technology decision for DeLimerence. The LLM must support anti-warmth system prompts, deliver clinically accurate psychoeducation, and operate within a zero-data-retention DPA (INT-001). UK data residency is required (TC-1).

---

### Option 1A: Build Custom Solution

**Description**: Train or fine-tune a custom LLM for limerence recovery conversations.

**Technology Stack**: PyTorch, Hugging Face Transformers, RLHF pipeline, GPU infrastructure

**Effort Estimate**:

- **Development**: 24+ person-months (ML engineers, clinical data labelling, safety alignment)
- **Skills Required**: ML engineering, NLP, RLHF, clinical psychology for data curation
- **Timeline**: 18+ months to production-ready

**Cost Breakdown**:
| Cost Item | Year 1 | Year 2 | Year 3 | Notes |
|-----------|--------|--------|--------|-------|
| Development | GBP 240,000 | GBP 0 | GBP 0 | GBP 10,000/month x 24 months |
| GPU infrastructure (training) | GBP 48,000 | GBP 12,000 | GBP 12,000 | A100 GPU cluster |
| Inference infrastructure | GBP 24,000 | GBP 36,000 | GBP 48,000 | Scaling with users |
| Maintenance (30% of dev) | GBP 0 | GBP 72,000 | GBP 72,000 | Retraining, safety updates |
| **Total** | **GBP 312,000** | **GBP 120,000** | **GBP 132,000** | |
| **3-Year TCO** | | | **GBP 564,000** | |

**Pros**:

- Full control over model behaviour, anti-warmth tuning, and clinical accuracy
- No vendor dependency for core capability
- IP ownership of fine-tuned model

**Cons**:

- Prohibitively expensive for a startup/prototype phase
- 18+ month timeline conflicts with Q4 2026 beta target (BC-1)
- Requires ML engineering team that does not yet exist
- Safety alignment for mental health is an unsolved research problem
- Clinical data for fine-tuning is extremely scarce (single published case study)

**Risks**:

- Model quality may not match frontier models: Mitigate by starting with API, evaluating custom model later
- Safety alignment failure: Mitigate with external safety layer regardless

**When to Build**: Only if DeLimerence reaches scale where API costs exceed infrastructure costs (likely 100,000+ daily sessions) and the clinical evidence base matures enough for fine-tuning.

---

### Option 1B: Buy - Anthropic Claude API (via AWS Bedrock)

**Description**: Use Anthropic Claude models via AWS Bedrock for UK data residency, with zero-retention data processing agreement. Claude's safety-focused training and Constitutional AI approach align well with the clinical safety requirements.

**Vendor**: Anthropic (San Francisco, founded 2021), accessed via AWS Bedrock (eu-west-2 London region)

**Pricing Model**: Per-token (input/output), usage-based

**Cost Breakdown**:
| Cost Item | Year 1 | Year 2 | Year 3 | Notes |
|-----------|--------|--------|--------|-------|
| Setup/onboarding | GBP 0 | GBP 0 | GBP 0 | Self-service API |
| API usage (Claude Sonnet 4.6) | GBP 9,600 | GBP 19,200 | GBP 38,400 | See calculation below |
| Bedrock regional premium (10%) | GBP 960 | GBP 1,920 | GBP 3,840 | UK regional endpoint |
| Integration development | GBP 4,000 | GBP 0 | GBP 0 | 2 person-weeks |
| **Total** | **GBP 14,560** | **GBP 21,120** | **GBP 42,240** | |
| **3-Year TCO** | | | **GBP 77,920** | |

**Usage Calculation**:

- Year 1: 1,000 daily sessions x 20 exchanges x ~2,000 tokens/exchange = 40M tokens/day
- At Claude Sonnet 4.6 pricing: $3/M input, $15/M output (approx 60:40 input:output ratio)
- Estimated ~GBP 800/month Year 1, scaling to GBP 3,200/month Year 3 at 20,000 daily sessions
- Prompt caching reduces repeat system prompt costs by up to 90%

**Pricing Tiers**:

- **Claude Haiku 4.5**: $1/$5 per M tokens - Budget option, may lack nuance for clinical conversations
- **Claude Sonnet 4.6**: $3/$15 per M tokens - Recommended balance of capability and cost
- **Claude Opus 4.6**: $5/$25 per M tokens - Premium, for most complex clinical scenarios

**Estimated Tier for This Project**: Claude Sonnet 4.6 for production conversations, with potential Haiku fallback for non-clinical interactions (e.g., ritual tracking data entry).

**Pros**:

- Claude's Constitutional AI training produces the most safety-aware responses of any frontier model
- System prompt adherence is strong -- critical for anti-warmth constraints (FR-007)
- AWS Bedrock provides UK data residency via eu-west-2 regional endpoint
- Zero-retention DPA available through Bedrock (INT-001 privacy requirement)
- Anthropic DPA automatically covers GDPR, updated January 2026
- ISO 27001:2022 and SOC 2 Type II certified
- Prompt caching reduces costs by up to 90% for system prompt tokens
- Batch API provides 50% discount for async workloads (e.g., outcome report generation)

**Cons**:

- No dedicated UK inference endpoint via direct Anthropic API (must use Bedrock)
- Bedrock regional endpoints carry 10% price premium
- Vendor dependency on both Anthropic and AWS
- Model updates may change conversational behaviour (requires clinical re-validation per NFR-M-001)
- Token-based pricing makes cost prediction harder than subscription model

**Key Features**:

- 1M token context window (sufficient for full session context + persistent data summary)
- Streaming support for real-time conversational UX
- Tool use / function calling for structured ritual tracking data extraction
- Vision capability (not needed for DeLimerence v1 but future-proofs for image-based assessments)

**Integration**:

- **APIs**: REST API via AWS Bedrock SDK, OpenAI-compatible endpoint
- **SDKs**: Python, JavaScript/TypeScript, Go
- **Authentication**: AWS IAM + API keys via Secrets Manager
- **Documentation**: Excellent -- comprehensive, well-structured, with cookbook examples

**Compliance & Security**:

- GDPR compliant (DPA covers UK GDPR)
- ISO 27001:2022 certified
- ISO 42001 (AI Management System) certified
- SOC 2 Type I & II
- UK data residency available via AWS Bedrock eu-west-2
- Zero-retention option (no request/response data stored at rest)
- Encryption at rest and in transit

**Vendor Maturity**:

- **Founded**: 2021
- **Funding**: Series E, $15B+ raised, valued at $61.5B (2025)
- **Customers**: Used by Notion, DuckDuckGo, Quora, government agencies
- **Market Position**: Leader in AI safety, top-3 LLM provider
- **Financial Stability**: Strong -- substantial funding runway

**Support**:

- **Support Tiers**: Developer forum, email, enterprise support (via Bedrock)
- **SLA**: 99.9% via AWS Bedrock SLA
- **Community**: Active developer community, comprehensive documentation

**Exit Strategy**:

- **Data Export**: No vendor-stored data (zero retention)
- **Migration Effort**: 2-4 person-weeks to switch to alternative LLM provider (system prompt + integration layer)
- **Lock-in Risk**: LOW -- standard API interface, abstraction layer recommended

**References**:

- Anthropic API documentation: https://platform.claude.com/docs
- AWS Bedrock Claude integration: https://docs.aws.amazon.com/bedrock/
- Anthropic GDPR compliance: https://www.waimakers.com/en/resources/gdpr-compliance/claude-anthropic

---

### Option 1C: Buy - OpenAI GPT API (via Azure OpenAI Service)

**Description**: Use OpenAI GPT models via Azure OpenAI Service for UK data residency, with zero-retention and GDPR-compliant DPA.

**Vendor**: OpenAI (San Francisco, founded 2015), accessed via Microsoft Azure (UK South region)

**Pricing Model**: Per-token, usage-based

**Cost Breakdown**:
| Cost Item | Year 1 | Year 2 | Year 3 | Notes |
|-----------|--------|--------|--------|-------|
| Setup/onboarding | GBP 0 | GBP 0 | GBP 0 | Self-service API |
| API usage (GPT-4o) | GBP 7,200 | GBP 14,400 | GBP 28,800 | Comparable usage to Claude estimate |
| Integration development | GBP 4,000 | GBP 0 | GBP 0 | 2 person-weeks |
| **Total** | **GBP 11,200** | **GBP 14,400** | **GBP 28,800** | |
| **3-Year TCO** | | | **GBP 54,400** | |

**Pros**:

- Largest ecosystem and tooling support
- Azure OpenAI Service provides UK South data residency
- Zero data retention available for API and ChatGPT Enterprise
- UK data residency confirmed for eligible customers
- DPA covers UK GDPR
- Competitive pricing (GPT-4o at $2.50/M input tokens)

**Cons**:

- Less safety-focused training than Claude's Constitutional AI approach
- Historically weaker system prompt adherence -- risk of warmth leakage in anti-warmth scenarios
- Azure OpenAI Service requires separate approval process
- OpenAI governance structure has undergone significant changes -- stability concern
- Model updates less predictable; safety characteristics may shift

**Compliance & Security**:

- GDPR compliant (DPA covers UK GDPR)
- SOC 2 Type II
- UK data residency via Azure UK South
- Zero data retention option
- Encryption at rest and in transit

**Vendor Maturity**:

- **Founded**: 2015
- **Funding**: Multi-billion Microsoft investment
- **Market Position**: Market leader by usage volume
- **Financial Stability**: Strong -- Microsoft backing

**Exit Strategy**:

- **Lock-in Risk**: LOW -- standard API interface

---

### Option 1D: Buy - Google Gemini API (via Vertex AI)

**Description**: Use Google Gemini models via Vertex AI with UK data residency (europe-west2, London).

**Vendor**: Google DeepMind / Google Cloud

**Pricing Model**: Per-token, usage-based

**Cost Breakdown**:
| Cost Item | Year 1 | Year 2 | Year 3 | Notes |
|-----------|--------|--------|--------|-------|
| API usage (Gemini 2.5 Pro) | GBP 6,000 | GBP 12,000 | GBP 24,000 | Lower per-token cost |
| Integration development | GBP 4,000 | GBP 0 | GBP 0 | 2 person-weeks |
| **Total** | **GBP 10,000** | **GBP 12,000** | **GBP 24,000** | |
| **3-Year TCO** | | | **GBP 46,000** | |

**Pros**:

- Lowest per-token cost (Gemini 2.5 Flash at $0.30/$2.50 per M tokens)
- UK data residency confirmed for Vertex AI europe-west2 (April 2026)
- Google guarantees data only resides in designated locations
- Free tier available for prototyping

**Cons**:

- Weaker system prompt adherence than Claude for safety-critical applications
- Less mature safety alignment for mental health contexts
- Gemini 2.5 model availability varies by region -- not all models available in europe-west2
- Google Cloud has smaller UK healthcare presence than AWS or Azure

**Exit Strategy**:

- **Lock-in Risk**: LOW -- standard API interface

---

### Build vs Buy Recommendation for LLM Foundation Model

**Recommended Approach**: BUY: Anthropic Claude Sonnet 4.6 via AWS Bedrock (eu-west-2)

**Rationale**:

Building a custom model is prohibitively expensive and misaligned with the Q4 2026 beta timeline. Among commercial options, Claude's Constitutional AI safety training provides the strongest foundation for anti-warmth system prompt adherence -- the single most critical technical requirement for DeLimerence (FR-007). While OpenAI GPT-4o is cheaper and Gemini is cheapest, the risk of warmth leakage in a tool designed to prevent attachment is unacceptable. Claude's safety focus directly serves DeLimerence's clinical requirements.

AWS Bedrock provides UK data residency (eu-west-2) with zero-retention DPA, satisfying TC-1 and INT-001. The 10% regional premium is a worthwhile cost for guaranteed UK data processing. The abstraction provided by the Vercel AI SDK (or a custom LLM client layer) means switching providers later is a 2-4 week effort, keeping lock-in risk low.

**Key Decision Factors**:

- **Safety-first training**: Claude's Constitutional AI approach reduces the risk of warmth-signalling responses that could trigger limerence transfer (BR-002)
- **UK data residency**: AWS Bedrock eu-west-2 satisfies TC-1 with zero-retention DPA for sensitive health data
- **Cost efficiency**: Prompt caching (90% reduction on system prompt tokens) and Sonnet-tier pricing keep costs manageable at startup scale

**Shortlist for Further Evaluation**:

1. **Anthropic Claude Sonnet 4.6 via AWS Bedrock**: Recommended -- best safety profile
2. **OpenAI GPT-4o via Azure OpenAI Service**: Alternative -- lower cost, weaker safety alignment

**Next Steps**:

- [ ] Conduct safety testing sprint: test system prompt adherence across 500+ adversarial scenarios
- [ ] Negotiate AWS Bedrock pricing for committed usage (potential 35% savings plan)
- [ ] Validate Claude response quality for all 4 limerence phases with clinical advisory board
- [ ] Establish system prompt version control workflow (NFR-M-001)

---

## Category 2: LLM Safety and Guardrails Layer

**Requirements Addressed**: NFR-SEC-006, FR-007, FR-011, NFR-C-003

**Why This Category**: All LLM responses must pass through a safety filter before delivery to the user (NFR-SEC-006). The filter must check for warmth-signalling language, diagnostic claims, harmful advice, system prompt disclosure, and off-topic responses. This is a unique requirement -- no off-the-shelf product addresses the anti-warmth clinical safety needs of DeLimerence.

---

### Option 2A: Build Custom Safety Layer

**Description**: Build a bespoke safety layer that filters LLM responses for anti-warmth violations, diagnostic claims, harmful content, and off-topic responses, using a combination of rule-based checks, classifier models, and a secondary LLM review pass.

**Technology Stack**: Python, regex/NLP classifiers, secondary LLM call for review, custom warmth-detection classifier

**Effort Estimate**:

- **Development**: 6 person-months
- **Skills Required**: NLP engineering, clinical psychology input for warmth taxonomy
- **Timeline**: 3 months to production-ready (parallel with LLM integration)

**Cost Breakdown**:
| Cost Item | Year 1 | Year 2 | Year 3 | Notes |
|-----------|--------|--------|--------|-------|
| Development | GBP 60,000 | GBP 0 | GBP 0 | GBP 10,000/month x 6 months |
| Secondary LLM calls (review) | GBP 2,400 | GBP 4,800 | GBP 9,600 | ~30% of primary LLM cost |
| Maintenance (30%) | GBP 0 | GBP 18,000 | GBP 18,000 | Ongoing refinement |
| **Total** | **GBP 62,400** | **GBP 22,800** | **GBP 27,600** | |
| **3-Year TCO** | | | **GBP 112,800** | |

**Pros**:

- Fully tailored to DeLimerence's unique anti-warmth requirements
- Can implement clinical-specific checks (diagnostic claim detection, warmth taxonomy)
- Full control over false positive/negative trade-offs
- IP ownership of safety methodology

**Cons**:

- Highest development cost
- Requires ongoing clinical review to maintain warmth taxonomy
- No community support -- all maintenance falls on the team

---

### Option 2B: Adopt - NVIDIA NeMo Guardrails + Custom Extensions

**Description**: Use NeMo Guardrails as the framework for conversation flow control, topic restriction, and basic safety, then extend with custom validators for DeLimerence-specific checks (anti-warmth detection, diagnostic claim filtering, clinical safety rules).

**Project Details**:

- **License**: Apache 2.0
- **GitHub**: https://github.com/NVIDIA-NeMo/Guardrails (5,600+ stars)
- **Maturity**: Stable, production-ready (Kubernetes deployment via Helm charts)
- **Last Release**: 2026 (active development)
- **Commit Activity**: Active
- **Contributors**: NVIDIA team + community

**Cost Breakdown** (Self-hosted on AWS):
| Cost Item | Year 1 | Year 2 | Year 3 | Notes |
|-----------|--------|--------|--------|-------|
| Infrastructure | GBP 1,200 | GBP 1,800 | GBP 2,400 | Fargate containers |
| Custom extension development | GBP 30,000 | GBP 0 | GBP 0 | 3 person-months for anti-warmth + clinical checks |
| Secondary LLM calls (guardrail checks) | GBP 1,800 | GBP 3,600 | GBP 7,200 | NeMo uses LLM for some checks |
| Maintenance | GBP 0 | GBP 9,000 | GBP 9,000 | Ongoing refinement |
| **Total** | **GBP 33,000** | **GBP 14,400** | **GBP 18,600** | |
| **3-Year TCO** | | | **GBP 66,000** | |

**Pros**:

- Production-ready framework reduces build effort by ~50%
- OpenAI-compatible API makes integration straightforward
- IORails engine supports parallel execution of multiple guardrails (50-200ms latency)
- Supports Anthropic, OpenAI, and open-source models
- LangChain integration via GuardrailsMiddleware
- Active NVIDIA maintenance and community
- Apache 2.0 license -- no restrictions on commercial use

**Cons**:

- Still requires custom extensions for anti-warmth and clinical checks (~3 months)
- NVIDIA dependency for framework updates
- Learning curve for Colang configuration language
- Additional LLM calls for some guardrail checks increase latency and cost

**Technical Considerations**:

- **Skills Required**: Python, NeMo Guardrails Colang syntax, NLP classifier development
- **Operational Burden**: Low -- containerised deployment, standard monitoring
- **Community Support**: NVIDIA developer forum, GitHub issues
- **Latency Impact**: 50-200ms per request (within NFR-P-001 5-second budget)

---

### Option 2C: Adopt - Guardrails AI + Custom Validators

**Description**: Use Guardrails AI framework for output validation with custom validators for clinical safety checks.

**Project Details**:

- **License**: Apache 2.0
- **GitHub**: https://github.com/guardrails-ai/guardrails
- **Maturity**: Stable
- **Hub**: 50+ pre-built validators

**Cost Breakdown**:
| Cost Item | Year 1 | Year 2 | Year 3 | Notes |
|-----------|--------|--------|--------|-------|
| Custom validator development | GBP 30,000 | GBP 0 | GBP 0 | 3 person-months |
| Infrastructure | GBP 600 | GBP 600 | GBP 600 | Lightweight, runs in-process |
| Maintenance | GBP 0 | GBP 9,000 | GBP 9,000 | |
| **Total** | **GBP 30,600** | **GBP 9,600** | **GBP 9,600** | |
| **3-Year TCO** | | | **GBP 49,800** | |

**Pros**:

- Output-focused validation (complements NeMo's flow control)
- 50+ pre-built validators (PII detection, toxicity, etc.)
- Lightweight -- runs in-process, minimal latency
- Composable validator architecture

**Cons**:

- Focuses on output validation, not conversation flow control
- Less mature for conversational AI use cases than NeMo
- Custom validators still needed for clinical specifics

---

### Build vs Buy Recommendation for Safety Layer

**Recommended Approach**: ADOPT: NVIDIA NeMo Guardrails + Custom Clinical Extensions

**Rationale**:

No off-the-shelf product addresses the unique anti-warmth and clinical safety requirements of DeLimerence. However, building entirely from scratch is unnecessary when NeMo Guardrails provides a production-ready framework for conversation flow control, topic restriction, and basic safety. The recommended approach uses NeMo for the framework (flow control, topic safety, jailbreak detection) and builds custom extensions for the DeLimerence-specific requirements: anti-warmth detection, diagnostic claim filtering, and phase-appropriate response validation.

This reduces development from 6 person-months (pure custom) to 3 person-months while providing a maintained, battle-tested foundation. The IORails engine's parallel execution keeps guardrail latency within the 5-second response budget (NFR-P-001).

A secondary recommendation is to layer Guardrails AI validators for output-level checks (PII detection, toxicity scoring) on top of NeMo's flow control, creating defence-in-depth.

**Next Steps**:

- [ ] Develop anti-warmth taxonomy with clinical advisory board (warmth-signalling language categories)
- [ ] Prototype NeMo Guardrails integration with Claude API (2-week POC)
- [ ] Train lightweight warmth-detection classifier on labelled conversation data

---

## Category 3: Authentication and User Management

**Requirements Addressed**: FR-010, FR-013, NFR-SEC-001, NFR-SEC-002, NFR-C-001, DR-001

**Why This Category**: Users must create accounts with age verification (18+), consent management, and minimal data collection (FR-010). The system needs role-based access control (NFR-SEC-002), session management with 30-minute inactivity timeout and 2-hour absolute timeout (NFR-SEC-001), and multi-account prevention (FR-013). UK GDPR compliance is mandatory.

---

### Option 3A: Build Custom Authentication

**Description**: Build authentication from scratch using bcrypt/argon2 password hashing, JWT sessions, and custom consent management.

**Effort Estimate**: 4 person-months

**Cost Breakdown**:
| Cost Item | Year 1 | Year 2 | Year 3 | Notes |
|-----------|--------|--------|--------|-------|
| Development | GBP 40,000 | GBP 0 | GBP 0 | 4 person-months |
| Maintenance | GBP 0 | GBP 12,000 | GBP 12,000 | Security patches, features |
| **Total** | **GBP 40,000** | **GBP 12,000** | **GBP 12,000** | |
| **3-Year TCO** | | | **GBP 64,000** | |

**Pros**:

- Full control over consent flow design for compromised executive function (FR-010)
- Custom session timeout logic (aligns with anti-dependency architecture)
- No external dependency for security-critical component

**Cons**:

- Authentication is a solved problem -- building it introduces security risk
- Maintaining security patches is an ongoing burden
- No built-in MFA, social login, or advanced features

---

### Option 3B: Buy - Supabase Auth (bundled with Supabase)

**Description**: Supabase provides authentication bundled with PostgreSQL database, row-level security, and real-time subscriptions. Auth supports email/password, magic links, MFA, and custom claims for RBAC.

**Vendor**: Supabase (Singapore, founded 2020), open-core model

**Pricing Model**: Usage-based (MAUs) with generous free tier

**Cost Breakdown**:
| Cost Item | Year 1 | Year 2 | Year 3 | Notes |
|-----------|--------|--------|--------|-------|
| Supabase Pro (auth + database) | GBP 300 | GBP 300 | GBP 300 | GBP 25/month Pro tier |
| Additional MAUs | GBP 0 | GBP 50 | GBP 160 | Beyond 100K MAUs at GBP 0.0026/MAU |
| Compute add-ons | GBP 600 | GBP 1,200 | GBP 2,400 | Scale as needed |
| Integration development | GBP 4,000 | GBP 0 | GBP 0 | 2 person-weeks |
| **Total** | **GBP 4,900** | **GBP 1,550** | **GBP 2,860** | |
| **3-Year TCO** | | | **GBP 9,310** | |

**Pricing Tiers**:

- **Free**: GBP 0/month - 50,000 MAUs, 500MB database, 1GB storage
- **Pro**: GBP 25/month - 100,000 MAUs, 8GB database, 100GB storage
- **Team**: GBP 599/month - SOC 2 Type 2, priority support
- **Enterprise**: Custom - HIPAA compliance, dedicated support

**Estimated Tier for This Project**: Pro tier (Year 1-2), Team tier (Year 3 for SOC 2)

**Pros**:

- 50,000 free MAUs covers entire Year 1 user base (5,000 projected users)
- Combined auth + database eliminates separate database procurement
- PostgreSQL with row-level security supports RBAC (NFR-SEC-002)
- Email/password auth with optional MFA (NFR-SEC-001)
- GDPR compliant with DPA available
- SOC 2 Type 2 (Team tier)
- Encryption at rest and in transit
- Open-source core -- self-hosting option as exit strategy
- Real-time subscriptions useful for cooldown timer updates

**Cons**:

- No dedicated UK region -- data centres in US, EU (Frankfurt), Singapore
- EU region (Frankfurt) may satisfy UK GDPR but is not UK soil
- HIPAA BAA requires Enterprise tier (may be needed if MHRA classifies as device)
- Session timeout customisation requires custom middleware (not built-in)
- Multi-account prevention (FR-013) requires custom logic on top of Supabase

**Integration**:

- **APIs**: REST, GraphQL, real-time WebSockets
- **SDKs**: JavaScript, Python, Dart, Swift, Kotlin
- **Authentication**: Built-in OAuth 2.0, JWT
- **Documentation**: Excellent

**Exit Strategy**:

- **Data Export**: Standard PostgreSQL export
- **Migration Effort**: 2-4 person-weeks (auth migration is most complex)
- **Lock-in Risk**: LOW -- open-source core, standard PostgreSQL

---

### Option 3C: Buy - Auth0 (by Okta)

**Description**: Enterprise identity platform with comprehensive authentication, MFA, social login, and compliance features.

**Vendor**: Auth0 / Okta (San Francisco)

**Pricing Model**: Per-MAU

**Cost Breakdown**:
| Cost Item | Year 1 | Year 2 | Year 3 | Notes |
|-----------|--------|--------|--------|-------|
| Subscription | GBP 2,520 | GBP 5,040 | GBP 12,600 | GBP 0.056/MAU, scaling with users |
| Integration development | GBP 2,000 | GBP 0 | GBP 0 | 1 person-week |
| **Total** | **GBP 4,520** | **GBP 5,040** | **GBP 12,600** | |
| **3-Year TCO** | | | **GBP 22,160** | |

**Pros**:

- Enterprise-grade compliance (SOC 2, ISO 27001, HIPAA BAA)
- Most comprehensive MFA and SSO options
- EU data residency available
- Best choice if MHRA classification requires healthcare-grade identity

**Cons**:

- Significantly more expensive than Supabase at scale (GBP 0.056/MAU vs GBP 0.0026/MAU)
- Over-engineered for DeLimerence's simple auth needs
- Does not bundle database -- separate procurement required

---

### Option 3D: Buy - Clerk

**Description**: Developer-focused authentication with modern React component library.

**Vendor**: Clerk (San Francisco)

**Pricing Model**: Per-MAU after free tier

**Cost Breakdown**:
| Cost Item | Year 1 | Year 2 | Year 3 | Notes |
|-----------|--------|--------|--------|-------|
| Subscription | GBP 300 | GBP 600 | GBP 1,500 | Pro tier + MAU overages |
| Integration development | GBP 2,000 | GBP 0 | GBP 0 | 1 person-week |
| **Total** | **GBP 2,300** | **GBP 600** | **GBP 1,500** | |
| **3-Year TCO** | | | **GBP 4,400** | |

**Pros**:

- Excellent developer experience with pre-built React components
- SOC 2 Type 2 across all tiers
- Free tier covers 50,000 monthly retained users
- Modern, purpose-built for Next.js/React

**Cons**:

- No UK data residency option -- fully managed, no self-hosting
- No HIPAA BAA outside Enterprise tier
- No database bundled -- separate procurement required
- Relatively young company (higher vendor viability risk)

---

### Build vs Buy Recommendation for Authentication

**Recommended Approach**: BUY: Supabase (Auth + Database combined)

**Rationale**:

Supabase provides the best value proposition by bundling authentication with PostgreSQL database, addressing two research categories with one platform. The 50,000 free MAU tier covers the entire Year 1 user base (5,000 projected users), and the Pro tier at GBP 25/month is dramatically cheaper than Auth0. While Supabase lacks a dedicated UK data centre, its EU (Frankfurt) region is GDPR-adequate for UK data processing. If MHRA classification triggers medical device requirements, the Team tier provides SOC 2 Type 2 certification, and the Enterprise tier adds HIPAA BAA.

The primary risk is the EU data residency gap. If strict UK-soil data residency is mandated (beyond GDPR adequacy), Auth0 with a separate UK-hosted PostgreSQL instance would be the fallback.

Custom consent flow design for compromised executive function (FR-010) will need to be built as application logic regardless of auth provider choice -- no provider offers this out of the box.

**Next Steps**:

- [ ] Confirm with legal counsel whether EU (Frankfurt) data residency satisfies project requirements or UK-soil is mandated
- [ ] Prototype Supabase Auth integration with Next.js (1-week POC)
- [ ] Design custom consent flow for compromised executive function

---

## Category 4: Database and Persistent Storage

**Requirements Addressed**: DR-001, DR-002, DR-003, DR-004, NFR-SEC-003, NFR-S-002, NFR-C-001

**Why This Category**: DeLimerence requires persistent cross-session storage for user profiles (DR-001), session data (DR-002), ritual tracking (DR-003), and self-assessment scores (DR-004). Data must be encrypted at rest with AES-256 and field-level encryption for sensitive content (NFR-SEC-003). UK data residency is required (TC-1). Data volume scales to 10TB over 3 years (NFR-S-002).

---

### Option 4A: Supabase PostgreSQL (bundled with Auth -- see Category 3)

**Description**: PostgreSQL database bundled with Supabase Auth, providing row-level security, real-time subscriptions, and managed backups.

**Cost**: Included in Supabase pricing (Category 3) -- no additional database procurement needed.

**Pros**:

- Already selected for authentication -- zero additional procurement
- PostgreSQL row-level security maps directly to RBAC requirements (NFR-SEC-002)
- Real-time subscriptions useful for cooldown timer and session state
- Managed backups (daily for Pro tier)
- Encryption at rest and in transit
- Open-source core (self-host option)

**Cons**:

- 8GB database on Pro tier may be tight for Year 3 scale (10TB requirement)
- EU data residency only (Frankfurt) -- not UK soil
- Field-level encryption (NFR-SEC-003) must be implemented at application layer
- Hourly backup RPO (NFR-A-002) requires custom configuration

**Recommendation**: Use Supabase PostgreSQL as primary database for Year 1-2. Plan migration to AWS RDS PostgreSQL (eu-west-2) if UK-soil data residency becomes mandated or data volume exceeds Supabase Team tier limits.

---

### Option 4B: AWS RDS PostgreSQL (eu-west-2 London)

**Description**: Fully managed PostgreSQL on AWS with UK data residency, Multi-AZ deployment, and automated backups.

**Cost Breakdown**:
| Cost Item | Year 1 | Year 2 | Year 3 | Notes |
|-----------|--------|--------|--------|-------|
| RDS db.t4g.medium (Multi-AZ) | GBP 1,800 | GBP 1,800 | GBP 3,600 | Scaling Year 3 |
| Storage (gp3, 100GB-1TB) | GBP 600 | GBP 1,200 | GBP 3,600 | Growing with data |
| Backup storage | GBP 120 | GBP 240 | GBP 720 | 90-day retention |
| Setup | GBP 2,000 | GBP 0 | GBP 0 | 1 person-week |
| **Total** | **GBP 4,520** | **GBP 3,240** | **GBP 7,920** | |
| **3-Year TCO** | | | **GBP 15,680** | |

**Pros**:

- UK data residency (eu-west-2 London) -- UK soil
- Multi-AZ for 99.95% availability
- Automated backups with point-in-time recovery (1-second RPO, exceeds NFR-A-002)
- Encryption at rest (AES-256) and in transit (TLS 1.3)
- Scales to 10TB+ without migration
- Integrates with AWS Secrets Manager for credential rotation

**Cons**:

- More expensive than Supabase for small scale
- Requires separate auth solution
- Operational complexity (patching, monitoring, scaling)

**Recommendation**: Fallback option if UK-soil data residency is mandated or scale exceeds Supabase limits.

---

### Build vs Buy Recommendation for Database

**Recommended Approach**: BUY: Supabase PostgreSQL (bundled with Auth) for Year 1-2; plan AWS RDS migration path for Year 3+ scale

**Rationale**:

Supabase eliminates the need for separate database procurement by bundling PostgreSQL with authentication. For Year 1 (5,000 users, ~500K sessions), the Pro tier is more than adequate. The migration path to AWS RDS PostgreSQL (eu-west-2) provides a clear exit strategy if data residency requirements tighten or data volume exceeds Supabase limits.

Field-level encryption for session transcripts and ritual tracking data (NFR-SEC-003) must be implemented at the application layer using pgcrypto or application-level AES-256 encryption, regardless of database provider choice.

---

## Category 5: Cloud Hosting and Infrastructure

**Requirements Addressed**: NFR-A-001, NFR-A-002, NFR-S-001, NFR-P-002, TC-1, TC-3

**Why This Category**: The application requires 99.9% uptime (NFR-A-001), horizontal scaling to support 5x growth (NFR-S-001), UK data residency (TC-1), and server-side enforcement of session limits and cooldowns (TC-3). Disaster recovery requires 1-hour RPO and 4-hour RTO (NFR-A-002).

---

### Option 5A: AWS (eu-west-2 London Region)

**Description**: AWS provides the broadest managed service catalogue with a dedicated UK region (eu-west-2, London). Recommended stack: ECS Fargate (serverless containers), ALB (load balancer), CloudWatch (monitoring), Secrets Manager, and WAF.

**Cost Breakdown**:
| Cost Item | Year 1 | Year 2 | Year 3 | Notes |
|-----------|--------|--------|--------|-------|
| ECS Fargate | GBP 2,400 | GBP 4,800 | GBP 9,600 | 2-4 tasks, auto-scaling |
| Application Load Balancer | GBP 600 | GBP 600 | GBP 600 | Fixed |
| CloudWatch | GBP 240 | GBP 480 | GBP 960 | Logs + metrics |
| Secrets Manager | GBP 24 | GBP 24 | GBP 24 | ~5 secrets at $0.40/secret/month |
| WAF | GBP 120 | GBP 120 | GBP 120 | Basic rules |
| S3 (static assets, backups) | GBP 60 | GBP 120 | GBP 240 | Growing with data |
| **Total** | **GBP 3,444** | **GBP 6,144** | **GBP 11,544** | |
| **3-Year TCO** | | | **GBP 21,132** | |

**Pros**:

- UK data residency (eu-west-2 London) -- data stays on UK soil
- AWS Bedrock in same region -- minimal latency for LLM calls
- Fargate eliminates server management (focus on application code)
- Auto-scaling built-in (NFR-S-001)
- 99.99% SLA for Multi-AZ deployments (exceeds NFR-A-001)
- Healthcare compliance tooling (AWS Artifact, HIPAA eligible)
- Secrets Manager with automatic rotation (NFR-SEC-004)
- Compute Savings Plans up to 66% discount

**Cons**:

- Most expensive of the three major cloud providers
- Complex pricing model (many dimensions)
- AWS knowledge required on team

---

### Option 5B: Azure (UK South Region)

**Description**: Azure provides UK South data centre with strong healthcare compliance. Recommended stack: Azure Container Apps, Azure Database for PostgreSQL, Azure Monitor.

**Cost Breakdown**:
| Cost Item | Year 1 | Year 2 | Year 3 | Notes |
|-----------|--------|--------|--------|-------|
| Container Apps | GBP 2,100 | GBP 4,200 | GBP 8,400 | Comparable to Fargate |
| Load Balancer | GBP 480 | GBP 480 | GBP 480 | |
| Monitor | GBP 240 | GBP 480 | GBP 960 | |
| Key Vault | GBP 24 | GBP 24 | GBP 24 | |
| **Total** | **GBP 2,844** | **GBP 5,184** | **GBP 9,864** | |
| **3-Year TCO** | | | **GBP 17,892** | |

**Pros**:

- UK South data centre
- Strong healthcare compliance (NHS Digital preferred supplier)
- Azure OpenAI Service if switching from Claude
- Slightly cheaper than AWS for comparable workloads

**Cons**:

- No Bedrock equivalent -- would need separate Anthropic API connection
- Container Apps less mature than Fargate
- Smaller ecosystem than AWS

---

### Build vs Buy Recommendation for Cloud Infrastructure

**Recommended Approach**: BUY: AWS eu-west-2 (London)

**Rationale**:

AWS provides the best alignment with the overall technology stack. AWS Bedrock (Claude) in the same region minimises latency for LLM calls, Secrets Manager satisfies NFR-SEC-004, and the breadth of managed services reduces operational burden. While Azure is slightly cheaper, the architectural coherence of running LLM, compute, storage, and secrets within a single cloud provider in the same UK region outweighs the cost difference.

The ECS Fargate serverless container approach eliminates server management, supports horizontal auto-scaling (NFR-S-001), and provides 99.99% Multi-AZ availability (exceeds NFR-A-001 target of 99.9%).

---

## Category 6: Application Framework (Web and Mobile)

**Requirements Addressed**: BR-001 (web and mobile), NFR-U-001 (anti-dependency UX), NFR-C-004 (WCAG 2.1 AA), NFR-P-001 (page load < 3 seconds)

**Why This Category**: DeLimerence must be available on web and mobile (BR-001) with a deliberately anti-companionable, clinical aesthetic (NFR-U-001). No push notifications, no animations, no gamification. WCAG 2.1 AA compliance required (NFR-C-004). The anti-dependency constraint (no push notifications, BC-2) eliminates a key advantage of native mobile apps.

---

### Option 6A: Next.js Progressive Web App (PWA)

**Description**: Build a single Next.js application that works as a responsive web app and can be installed as a PWA on mobile devices. Deployed as a containerised application on AWS ECS Fargate.

**Technology Stack**: Next.js 15+, React, TypeScript, Tailwind CSS, Vercel AI SDK (open-source, for LLM integration)

**Cost Breakdown**:
| Cost Item | Year 1 | Year 2 | Year 3 | Notes |
|-----------|--------|--------|--------|-------|
| Development | GBP 60,000 | GBP 0 | GBP 0 | 6 person-months |
| Maintenance | GBP 0 | GBP 18,000 | GBP 18,000 | 30% of dev |
| **Total** | **GBP 60,000** | **GBP 18,000** | **GBP 18,000** | |
| **3-Year TCO** | | | **GBP 96,000** | |

**Pros**:

- Single codebase for web and mobile
- PWA provides "Add to Home Screen" for mobile-app experience without app store
- No app store approval process (important: health apps face scrutiny on App Store/Play Store)
- Vercel AI SDK is free and open source -- provides streaming LLM response UI
- Next.js App Router + React Server Components for optimal performance
- Tailwind CSS enables clinical, minimal aesthetic (NFR-U-001)
- WCAG 2.1 AA achievable with standard React accessibility libraries
- No push notifications by default (aligns with BC-2 anti-dependency)
- Containerised deployment on AWS Fargate (not tied to Vercel hosting)
- Strong developer hiring market for React/Next.js

**Cons**:

- PWA on iOS has limited capabilities (no background processing, limited notifications)
- Not a native app -- may feel less polished on mobile
- PWA cannot send notifications to iOS users (a non-issue given BC-2)
- Requires server-side rendering infrastructure

---

### Option 6B: React Native (Cross-Platform Native)

**Description**: Build native mobile apps for iOS and Android with a shared React Native codebase, plus a separate web application.

**Cost Breakdown**:
| Cost Item | Year 1 | Year 2 | Year 3 | Notes |
|-----------|--------|--------|--------|-------|
| Development | GBP 100,000 | GBP 0 | GBP 0 | 10 person-months (mobile + web) |
| App store fees | GBP 180 | GBP 180 | GBP 180 | Apple + Google annual |
| Maintenance | GBP 0 | GBP 30,000 | GBP 30,000 | 30% of dev |
| **Total** | **GBP 100,180** | **GBP 30,180** | **GBP 30,180** | |
| **3-Year TCO** | | | **GBP 160,540** | |

**Pros**:

- True native mobile experience
- Better performance on mobile devices
- App Store presence for discoverability

**Cons**:

- 67% more expensive than PWA approach
- App Store health app review process adds regulatory risk
- Push notification capability conflicts with anti-dependency (must be deliberately disabled)
- Two codebases to maintain (or three if web is separate)
- App store approval creates gatekeeping risk

---

### Build vs Buy Recommendation for Application Framework

**Recommended Approach**: BUILD: Next.js PWA

**Rationale**:

The PWA approach is uniquely aligned with DeLimerence's anti-dependency architecture. The inability to send push notifications on iOS is normally a PWA limitation -- for DeLimerence, it is a feature. The clinical, minimal aesthetic (NFR-U-001) does not benefit from native mobile capabilities. The single codebase reduces development cost by 40% compared to React Native, and avoiding app store submission eliminates regulatory friction with Apple and Google health app review processes.

The Vercel AI SDK (free, open-source TypeScript library) provides streaming LLM response UI out of the box, reducing LLM integration effort. Deployment on AWS Fargate (not Vercel hosting) maintains UK data residency and avoids vendor lock-in.

---

## Category 7: Observability and Monitoring

**Requirements Addressed**: NFR-M-002, NFR-C-002, NFR-A-001

**Why This Category**: DeLimerence requires structured JSON logging, centralised aggregation, metrics (session counts, response latency, cooldown compliance rates, crisis event frequency), and alerts (LLM latency > 10s, crisis events, cooldown circumvention, error rate > 1%). Audit logging with tamper-evident integrity is required for compliance (NFR-C-002).

---

### Option 7A: Grafana Cloud (Free/Pro tier)

**Description**: Composable observability platform built on open standards (Prometheus, Loki, Tempo). Free tier includes 10K active metrics, 50GB logs, 50GB traces with 14-day retention.

**Cost Breakdown**:
| Cost Item | Year 1 | Year 2 | Year 3 | Notes |
|-----------|--------|--------|--------|-------|
| Platform fee | GBP 0 | GBP 228 | GBP 228 | Free Year 1; Pro at GBP 19/month Year 2+ |
| Additional usage | GBP 0 | GBP 600 | GBP 1,200 | Overage on logs/metrics |
| Integration development | GBP 2,000 | GBP 0 | GBP 0 | 1 person-week |
| **Total** | **GBP 2,000** | **GBP 828** | **GBP 1,428** | |
| **3-Year TCO** | | | **GBP 4,256** | |

**Pros**:

- Free tier covers Year 1 entirely (10K metrics, 50GB logs, 50GB traces)
- Open standards (Prometheus, Loki) -- no vendor lock-in
- Custom dashboards for DeLimerence-specific metrics (cooldown compliance, crisis events)
- Alerting built-in (Slack, PagerDuty, email)
- Usage-based pricing scales predictably

**Cons**:

- No built-in audit log integrity (tamper-evident logging for NFR-C-002 needs separate solution)
- 14-day retention on free tier (insufficient for 2-year compliance log retention)
- Pro tier needed for longer retention and support

---

### Option 7B: Datadog

**Description**: Fully managed end-to-end observability platform.

**Cost Breakdown**:
| Cost Item | Year 1 | Year 2 | Year 3 | Notes |
|-----------|--------|--------|--------|-------|
| Infrastructure monitoring | GBP 2,880 | GBP 5,760 | GBP 11,520 | Per-host pricing |
| Log management | GBP 1,200 | GBP 2,400 | GBP 4,800 | Per-GB ingestion |
| APM | GBP 3,600 | GBP 7,200 | GBP 14,400 | Per-host |
| Integration development | GBP 1,000 | GBP 0 | GBP 0 | Minimal |
| **Total** | **GBP 8,680** | **GBP 15,360** | **GBP 30,720** | |
| **3-Year TCO** | | | **GBP 54,760** | |

**Pros**:

- Most comprehensive feature set
- Excellent alerting and dashboards
- Strong APM and distributed tracing

**Cons**:

- 13x more expensive than Grafana Cloud over 3 years
- Complex multi-dimensional pricing
- Overkill for DeLimerence's scale

---

### Build vs Buy Recommendation for Observability

**Recommended Approach**: BUY: Grafana Cloud (Free tier Year 1, Pro Year 2+) + AWS CloudWatch for audit logs

**Rationale**:

Grafana Cloud's free tier covers Year 1 observability needs entirely, and the Pro tier at GBP 19/month is adequate for Year 2+. Custom dashboards will track DeLimerence-specific metrics: cooldown compliance rate, crisis event frequency, LLM response latency, and session completion rates.

For the tamper-evident audit logging requirement (NFR-C-002, 2-year retention), AWS CloudWatch Logs with log integrity validation provides immutable storage within the AWS eu-west-2 region. This is a separate concern from application observability and is better served by the cloud provider's native compliance tooling.

---

## Total Cost of Ownership (TCO) Summary

### Blended TCO Across All Categories

**Recommended Approach (Blended)**:

| Category | Recommended Option | Year 1 | Year 2 | Year 3 | 3-Year TCO |
|----------|-------------------|--------|--------|--------|------------|
| LLM Foundation Model | Claude via AWS Bedrock | GBP 14,560 | GBP 21,120 | GBP 42,240 | GBP 77,920 |
| LLM Safety Layer | NeMo Guardrails + Custom | GBP 33,000 | GBP 14,400 | GBP 18,600 | GBP 66,000 |
| Auth + Database | Supabase (bundled) | GBP 4,900 | GBP 1,550 | GBP 2,860 | GBP 9,310 |
| Cloud Infrastructure | AWS eu-west-2 | GBP 3,444 | GBP 6,144 | GBP 11,544 | GBP 21,132 |
| Application Framework | Next.js PWA (build) | GBP 60,000 | GBP 18,000 | GBP 18,000 | GBP 96,000 |
| Observability | Grafana Cloud + CloudWatch | GBP 2,240 | GBP 1,068 | GBP 1,668 | GBP 4,976 |
| Secrets Management | AWS Secrets Manager | GBP 24 | GBP 24 | GBP 24 | GBP 72 |
| **TOTAL** | | **GBP 118,168** | **GBP 62,306** | **GBP 94,936** | **GBP 275,410** |

### Alternative Scenarios

**Scenario A: Build Everything**:

- 3-Year TCO: GBP 836,800
- Pros: Maximum control and flexibility, full IP ownership
- Cons: 18+ month timeline (misses Q4 2026 target), requires ML team, highest risk

**Scenario B: Buy Everything (Commercial SaaS)**:

- 3-Year TCO: GBP 232,240
- Pros: Fastest time to market, managed services throughout
- Cons: No SaaS product addresses anti-warmth safety requirements (must build safety layer regardless); higher ongoing subscription costs; vendor lock-in across multiple providers

**Scenario C: Open Source Everything**:

- 3-Year TCO: GBP 310,000
- Pros: Lower licensing costs, flexibility, avoid lock-in
- Cons: Requires self-hosting LLM (GPU costs exceed API costs at this scale), significant operational burden, smaller team cannot maintain all components

**Scenario D: Recommended Blended Approach**:

- 3-Year TCO: GBP 275,410
- Pros: Balance of cost, speed, control, and risk; core IP (safety layer, UX) built in-house; commodity components (auth, hosting, monitoring) bought
- Cons: Multi-vendor management; Supabase EU data residency gap

### TCO Assumptions

- Engineering rates: GBP 500/day (blended rate for senior developers)
- Infrastructure: AWS UK region (eu-west-2) on-demand pricing
- SaaS pricing: List prices with 10% annual increases factored into Year 2-3
- Maintenance: 30% of development cost annually for custom-built components
- Exchange rates: 1 USD = 0.80 GBP (April 2026)
- LLM token usage: Based on 20 exchanges per session, ~2,000 tokens per exchange, with prompt caching

### Risk-Adjusted TCO

| Scenario | Base TCO | Contingency | Risk-Adjusted TCO | Risk Factors |
|----------|----------|-------------|-------------------|--------------|
| Build Everything | GBP 836,800 | +20% | GBP 1,004,160 | ML team recruitment, safety alignment failure, timeline overrun |
| Buy (SaaS) | GBP 232,240 | +10% | GBP 255,464 | Price increases, vendor changes, still requires custom safety layer |
| Open Source | GBP 310,000 | +15% | GBP 356,500 | Underestimated maintenance, GPU costs, operational complexity |
| Recommended | GBP 275,410 | +12% | GBP 308,459 | Supabase data residency gap, LLM API price changes |

---

## Requirements Traceability

### Requirements Coverage Matrix

| Requirement ID | Requirement Description | Research Category | Recommended Solution | Rationale |
|----------------|------------------------|-------------------|---------------------|-----------|
| FR-001 | Session limit enforcement (20 exchanges) | Application Framework | Custom build (Next.js) | Server-side counter in application logic |
| FR-002 | Cooldown period enforcement (8 hours) | Auth + Database | Custom logic on Supabase | Server-side timestamp comparison |
| FR-003 | Phase assessment engine | LLM + Safety Layer | Custom build (LLM system prompt + structured output) | No off-the-shelf phase assessment exists |
| FR-004 | Ritual tracking system | Database | Supabase PostgreSQL | Standard CRUD with time-series queries |
| FR-005 | Psychoeducation delivery engine | LLM Foundation Model | Claude via Bedrock (system prompt) | Context-aware delivery via LLM conversation |
| FR-006 | Action commitment gate | Application Framework | Custom build (Next.js) | Session flow control in application logic |
| FR-007 | Anti-warmth conversational behaviour | LLM + Safety Layer | Claude + NeMo Guardrails | System prompt + guardrail enforcement |
| FR-008 | ABCDE cognitive restructuring | LLM Foundation Model | Claude via Bedrock (system prompt) | Guided conversation flow via LLM |
| FR-009 | LLM foundation model integration | LLM Foundation Model | Claude Sonnet 4.6 via AWS Bedrock | Best safety profile, UK data residency |
| FR-010 | User account and authentication | Authentication | Supabase Auth | Email/password, MFA, consent management |
| FR-011 | Transparency and self-identification | Application Framework | Custom build (Next.js UX) | "Tool" labelling, transparency statements |
| FR-012 | ERP ritual resistance support | LLM Foundation Model | Claude via Bedrock (system prompt) | Conversational ERP guidance |
| FR-013 | Multi-account prevention | Authentication | Custom logic on Supabase Auth | Email dedup + device fingerprinting |
| FR-014 | Behavioural activation prompts | LLM Foundation Model | Claude via Bedrock (system prompt) | Activity suggestions via LLM |
| FR-015 | Research consent and data export | Auth + Database | Custom build on Supabase | Separate consent flow, 48-hour delay logic |
| FR-016 | Outcome self-assessment | Application + Database | Custom build (Next.js + Supabase) | Standardised instrument, score tracking |
| NFR-P-001 | Response time < 5s (p95) | LLM + Infrastructure | Claude Sonnet + NeMo ( < 200ms) + Fargate | Combined latency within budget |
| NFR-P-002 | 10K-50K sessions/day throughput | Infrastructure | AWS ECS Fargate auto-scaling | Horizontal scaling |
| NFR-A-001 | 99.9% uptime | Infrastructure | AWS Multi-AZ Fargate | 99.99% SLA exceeds target |
| NFR-A-002 | RPO 1 hour, RTO 4 hours | Database + Infrastructure | Supabase backups + AWS cross-region | Point-in-time recovery |
| NFR-A-003 | Graceful degradation | Application Framework | Custom build (circuit breaker) | Static fallback content on LLM outage |
| NFR-S-001 | Horizontal scaling | Infrastructure | AWS ECS Fargate | Auto-scaling on CPU/memory triggers |
| NFR-S-002 | Data volume to 10TB | Database | Supabase (Year 1-2), AWS RDS (Year 3+) | Migration path for scale |
| NFR-SEC-001 | Authentication with MFA | Authentication | Supabase Auth | Built-in MFA support |
| NFR-SEC-002 | RBAC with data isolation | Auth + Database | Supabase RLS + custom roles | PostgreSQL row-level security |
| NFR-SEC-003 | Encryption (AES-256, TLS 1.3) | Database + Infrastructure | Supabase + AWS | At-rest and in-transit encryption |
| NFR-SEC-004 | Secrets management | Infrastructure | AWS Secrets Manager | $0.40/secret/month, auto-rotation |
| NFR-SEC-005 | Vulnerability management | Infrastructure + DevOps | Custom CI/CD pipeline | SAST, DAST, dependency scanning |
| NFR-SEC-006 | LLM safety layer | Safety Layer | NeMo Guardrails + custom extensions | Anti-warmth, diagnostic claims, off-topic |
| NFR-C-001 | UK GDPR compliance | All categories | DPA from all vendors; UK data residency | Supabase EU, AWS UK |
| NFR-C-002 | Audit logging (2-year retention) | Observability | AWS CloudWatch Logs (immutable) | Tamper-evident, 2-year retention |
| NFR-C-003 | MHRA regulatory positioning | Application Framework | Custom UX design | "Not a therapist" messaging throughout |
| NFR-C-004 | WCAG 2.1 AA accessibility | Application Framework | Next.js + accessibility libraries | React aria, semantic HTML |
| NFR-U-001 | Anti-dependency UX | Application Framework | Custom build (Next.js) | Clinical aesthetic, no gamification |
| NFR-U-002 | Plain language | LLM + Application | Claude system prompt + content review | Flesch-Kincaid < grade 10 |
| NFR-M-001 | System prompt version control | Infrastructure | Git + clinical review workflow | PR-based with CAB reviewer |
| NFR-M-002 | Observability | Observability | Grafana Cloud + CloudWatch | Metrics, logs, traces, alerts |
| INT-001 | LLM API integration | LLM Foundation Model | Claude via AWS Bedrock | REST API, streaming, zero retention |
| INT-002 | Crisis resource API (optional) | Application Framework | Static dataset with periodic refresh | Fallback to static if API unavailable |
| INT-003 | Analytics and outcome reporting | Observability + Database | Custom build (Supabase queries + export) | Anonymised aggregate data |

### Coverage Summary

**Requirements with Identified Solutions**:

- 37 requirements (95%) have recommended commercial, open source, or custom solutions
- 2 requirements (5%) require custom development with no suitable off-the-shelf option:
  - FR-003 (Phase Assessment Engine) -- novel clinical logic, no existing product
  - NFR-SEC-006 (Clinical Safety Layer) -- unique anti-warmth requirements

**Gaps and Concerns**:

**GAP-1**: UK-soil data residency

- **Impact**: Supabase (EU Frankfurt) may not satisfy strict UK-soil data residency if required by MHRA or ICO
- **Options**: Migrate to AWS RDS PostgreSQL (eu-west-2) for database; use Auth0 for authentication
- **Recommendation**: Confirm with legal counsel; prepare AWS RDS migration path

**GAP-2**: MHRA classification uncertainty

- **Impact**: If MHRA classifies as medical device, all vendors need healthcare-grade compliance (HIPAA BAA, clinical evidence, quality management system)
- **Options**: Supabase Enterprise tier adds HIPAA; Auth0 has HIPAA BAA; phased launch mitigates
- **Recommendation**: Proceed with MHRA pre-submission meeting using Phase 1 (psychoeducation only) scope

---

## Integration with Wardley Mapping

Research findings inform Wardley Map value chain positioning and evolution:

### Value Chain Components by Evolution

| Component | Evolution Stage | Recommended Approach | Rationale |
|-----------|----------------|---------------------|-----------|
| Anti-Warmth Safety Layer | Genesis (novel) | Build Custom (on NeMo framework) | Unique to DeLimerence; no existing product |
| Phase Assessment Engine | Genesis (novel) | Build Custom | Clinical IP; novel application of limerence research |
| Limerence Psychoeducation Content | Custom | Build (with clinical advisory board) | Domain-specific content, no off-the-shelf |
| Anti-Dependency UX | Custom | Build Custom | Deliberate inversion of standard UX patterns |
| LLM Foundation Model | Product | Buy SaaS (Claude via Bedrock) | Mature market, frontier models available |
| Authentication | Commodity | Buy SaaS (Supabase Auth) | Solved problem, commodity service |
| Database (PostgreSQL) | Commodity | Buy Managed (Supabase) | Standard infrastructure |
| Cloud Hosting | Commodity | Buy IaaS (AWS) | Commodity infrastructure |
| Monitoring/Observability | Commodity | Buy SaaS (Grafana Cloud) | Standard tooling |
| Secrets Management | Commodity | Buy (AWS Secrets Manager) | Commodity utility |

**Strategic Insights**:

- The anti-warmth safety layer and phase assessment engine are the only Genesis-stage components and represent DeLimerence's core IP. These must be built in-house.
- The LLM foundation model is in the Product stage -- mature enough to buy, not yet commodity. Model selection matters but building is unjustified.
- Authentication, database, hosting, and monitoring are all commodity -- buying managed services is the only defensible approach.

**Next Steps**:

- Run `/arckit:wardley` to create Wardley Map with research findings
- Position components on evolution axis based on build/buy decisions
- Identify strategic plays (componentise novel features once mature)

---

## Integration with SOBC Economic Case

Research findings feed into Strategic Outline Business Case (SOBC) Economic Case:

### Options Analysis for SOBC

**Option 0: Do Nothing (Baseline)**

- Cost: GBP 0
- Benefits: None
- Risk: No defensive tool exists; AI-enabled limerence exploitation scales unchecked

**Option 1: Build Everything Custom**

- 3-Year TCO: GBP 1,004,160 (risk-adjusted)
- Benefits: Full IP ownership, maximum control
- Risks: 18+ month timeline, ML team recruitment, safety alignment failure

**Option 2: Recommended Blended Approach**

- 3-Year TCO: GBP 308,459 (risk-adjusted)
- Benefits: Q4 2026 beta achievable, core IP retained, commodity components managed
- Risks: Supabase data residency gap, multi-vendor management

**Option 3: Open Source Everything**

- 3-Year TCO: GBP 356,500 (risk-adjusted)
- Benefits: Lower licensing costs, maximum flexibility
- Risks: GPU infrastructure costs, operational burden exceeds small team capacity

**Preferred Option**: Option 2 -- Recommended Blended Approach

**Rationale**: Best value for money given the Q4 2026 timeline constraint (BC-1), small team size, and the need to retain IP on the novel safety and clinical components while minimising operational burden on commodity infrastructure.

### Cost Data for SOBC

**CAPEX (Initial Investment)**:

- Custom development (safety layer, application, integrations): GBP 98,000
- Setup/integration of managed services: GBP 12,000
- **Total CAPEX**: GBP 110,000

**OPEX (Ongoing Annual, from Year 2)**:

- LLM API usage: GBP 21,120-42,240/year (scaling)
- Infrastructure (AWS + Supabase): GBP 8,000-15,000/year (scaling)
- Maintenance (custom code): GBP 36,000/year
- Observability: GBP 1,000-1,500/year
- **Total OPEX**: GBP 66,120-94,740/year

---

## Vendor Shortlist for Further Evaluation

### Top 3 Vendors/Products Recommended

#### 1. Anthropic Claude (via AWS Bedrock) for LLM Foundation Model

**Overall Rating**: 4.5/5

**Strengths**:

- Constitutional AI safety training -- best-in-class for anti-warmth system prompt adherence
- UK data residency via AWS Bedrock eu-west-2
- Zero-retention DPA for sensitive health data
- ISO 27001, SOC 2 Type II certified
- Prompt caching reduces costs by up to 90%

**Concerns**:

- No direct Anthropic UK endpoint -- depends on AWS Bedrock
- Model updates may change safety characteristics (requires clinical re-validation)

**Next Steps**:

- [ ] Safety testing sprint: 500+ adversarial anti-warmth scenarios
- [ ] Negotiate AWS Bedrock committed usage pricing
- [ ] Clinical advisory board review of Claude response quality across all 4 phases
- [ ] Establish system prompt version control workflow

#### 2. Supabase for Authentication + Database

**Overall Rating**: 4/5

**Strengths**:

- Combined auth + PostgreSQL eliminates separate procurement
- 50,000 free MAUs covers Year 1 entirely
- GBP 25/month Pro tier is dramatically cost-effective
- Open-source core provides exit strategy
- Row-level security maps to RBAC requirements

**Concerns**:

- EU data residency only (Frankfurt) -- not UK soil
- HIPAA BAA requires Enterprise tier

**Next Steps**:

- [ ] Legal review: EU (Frankfurt) adequacy for UK health data
- [ ] Prototype integration with Next.js (1-week POC)
- [ ] Test row-level security for user data isolation
- [ ] Evaluate custom consent flow implementation

#### 3. AWS (eu-west-2 London) for Cloud Infrastructure

**Overall Rating**: 4.5/5

**Strengths**:

- UK data residency on UK soil
- Broadest managed service catalogue
- Bedrock integration for Claude in same region
- ECS Fargate eliminates server management
- Healthcare compliance tooling (AWS Artifact)
- Secrets Manager with automatic rotation

**Concerns**:

- Most expensive of major cloud providers
- Complex pricing model

**Next Steps**:

- [ ] Set up AWS account with eu-west-2 as default region
- [ ] Configure Bedrock access for Claude models
- [ ] Estimate Fargate costs using AWS Pricing Calculator
- [ ] Evaluate Compute Savings Plans for Year 2+

---

## Risks and Mitigations

### Vendor Risks

**VR-1: Anthropic Model Safety Drift**

- **Risk**: Future Claude model updates change safety characteristics, causing warmth leakage
- **Impact**: HIGH -- Undermines core anti-dependency architecture (BR-002)
- **Likelihood**: MEDIUM -- All LLM providers update models regularly
- **Mitigation**:
  - Pin to specific model version (Claude Sonnet 4.6) via Bedrock
  - NeMo Guardrails safety layer catches warmth regardless of model
  - Clinical re-validation test suite run on every model version change
  - System prompt version control with clinical advisory board approval (NFR-M-001)

**VR-2: Supabase Data Residency Gap**

- **Risk**: ICO or MHRA requires UK-soil data residency, Supabase only offers EU (Frankfurt)
- **Impact**: HIGH -- Compliance blocker
- **Likelihood**: LOW-MEDIUM -- UK GDPR adequacy with EU processing is currently accepted
- **Mitigation**:
  - Pre-prepared AWS RDS PostgreSQL (eu-west-2) migration path
  - Auth0 as fallback authentication provider (EU and UK data residency)
  - Legal counsel confirmation before committing to Supabase

**VR-3: AWS Bedrock Pricing Changes**

- **Risk**: AWS or Anthropic increase token pricing beyond budget
- **Impact**: MEDIUM -- Budget overrun on largest cost component
- **Likelihood**: LOW -- LLM API prices have decreased 80% year-over-year
- **Mitigation**:
  - Committed use pricing (Savings Plans) for 35% discount
  - Prompt caching reduces effective cost by up to 90%
  - Abstraction layer allows switching to Gemini or GPT if needed

### Technical Risks

**TR-1: Anti-Warmth Safety Layer Effectiveness**

- **Risk**: Custom safety layer fails to catch warmth-signalling responses reliably
- **Impact**: CRITICAL -- Core product requirement (BR-002)
- **Likelihood**: MEDIUM
- **Mitigation**:
  - Defence-in-depth: NeMo flow control + output validators + secondary LLM review
  - Continuous evaluation with adversarial test suite
  - Clinical advisory board quarterly safety review
  - User reporting mechanism for warmth leakage

### Compliance Risks

**CR-1: MHRA Classification as Medical Device**

- **Risk**: MHRA classifies DeLimerence as Class IIa medical device
- **Impact**: HIGH -- 12-18 month regulatory pathway, Notified Body assessment required
- **Likelihood**: MEDIUM -- CBT/ERP delivery may cross treatment boundary
- **Mitigation**:
  - Phased launch: Phase 1 psychoeducation only (lower risk)
  - MHRA pre-submission meeting to clarify classification
  - All vendors support healthcare-grade compliance if needed (Supabase Enterprise, AWS HIPAA)
  - MHRA/NICE AI airlock regulatory sandbox available

---

## Next Steps and Recommendations

### Immediate Actions (0-2 weeks)

1. **Legal Review**: Confirm UK data residency requirements (EU adequacy vs UK-soil mandate)
2. **AWS Account Setup**: Establish eu-west-2 region, configure Bedrock access
3. **Claude Safety Testing**: Begin 500-scenario adversarial testing sprint
4. **Supabase POC**: Prototype auth + database integration with Next.js

### Vendor Evaluation (2-6 weeks)

5. **LLM Comparison**: Run identical anti-warmth test suite on Claude, GPT-4o, and Gemini
6. **Supabase Data Residency**: Legal opinion on EU (Frankfurt) adequacy for UK health data
7. **NeMo Guardrails POC**: 2-week proof-of-concept for safety layer architecture
8. **Grafana Cloud Setup**: Configure free tier for development monitoring

### Decision and Procurement (6-12 weeks)

9. **Vendor Selection**: Finalise LLM provider based on safety testing results
10. **Infrastructure Setup**: AWS eu-west-2 production environment
11. **Development Sprint**: Begin Next.js PWA + Supabase integration

### Integration with Other Commands

12. **Create Wardley Map**: Run `/arckit:wardley` to map value chain with evolution positioning
13. **Generate SOBC**: Run `/arckit:sobc` to create Strategic Outline Business Case with TCO data
14. **Generate SOW**: Run `/arckit:sow` to create vendor RFP for shortlisted options

---

## Appendices

### Appendix A: Research Methodology

**Data Sources**:

- Vendor websites and pricing pages (Anthropic, OpenAI, Google Cloud, Supabase, Clerk, Auth0, AWS, Azure, Grafana, Datadog)
- G2, TrustRadius review comparisons
- GitHub repositories (NeMo Guardrails, Guardrails AI, Vercel AI SDK)
- UK Government MHRA guidance on digital mental health technologies
- NHS Confederation publications on clinical AI
- Parliamentary POST briefings on AI and mental healthcare
- UK government code repositories via govreposcrape (24,500+ repos searched)
- LLM pricing comparison sites (TLDL, CloudIDR, PricePerToken, BenchLM)

**Evaluation Criteria**:

- Requirements fit (MUST/SHOULD/COULD coverage)
- Pricing and TCO (3-year projection with 10% annual SaaS increase)
- Safety characteristics (critical for LLM provider selection)
- UK data residency (TC-1 compliance)
- Vendor maturity and financial stability
- Security and compliance (ISO 27001, SOC 2, GDPR, potential HIPAA)
- Integration complexity and documentation quality
- Exit strategy and lock-in risk

**Limitations**:

- Pricing based on list prices (enterprise discounts may be available)
- LLM API prices have been declining ~80% year-over-year; Year 2-3 projections may overestimate
- MHRA regulatory landscape is actively evolving (new framework expected 2026)
- Research valid for approximately 6 months given pace of LLM market

### Appendix B: Glossary

- **TCO**: Total Cost of Ownership (all costs over 3-year period)
- **CAPEX**: Capital Expenditure (initial investment)
- **OPEX**: Operational Expenditure (ongoing costs)
- **SaaS**: Software as a Service
- **PaaS**: Platform as a Service
- **IaaS**: Infrastructure as a Service
- **SLA**: Service Level Agreement
- **API**: Application Programming Interface
- **LLM**: Large Language Model
- **DPA**: Data Processing Agreement
- **MAU**: Monthly Active Users
- **PWA**: Progressive Web App
- **RBAC**: Role-Based Access Control
- **RLS**: Row-Level Security
- **RPO**: Recovery Point Objective
- **RTO**: Recovery Time Objective
- **MHRA**: Medicines and Healthcare products Regulatory Agency
- **ICO**: Information Commissioner's Office
- **CBT**: Cognitive Behavioural Therapy
- **ERP**: Exposure and Response Prevention
- **NeMo**: NVIDIA NeMo (Neural Modules)

### Appendix C: UK Government Code Reuse Assessment

A search of 24,500+ UK government repositories via govreposcrape found no directly reusable code for any DeLimerence research category. Search queries included:

- "mental health chatbot CBT therapeutic conversational AI" (1 result, unrelated)
- "authentication session management cooldown rate limiting" (3 results, unrelated -- GIS maps, Active Directory)
- "LLM guardrails safety filter content moderation" (5 results, unrelated -- CMS, asset library)

This is expected given the novel nature of an anti-dependency limerence recovery tool. No existing UK government implementation addresses this domain. The "Reuse Government Code" option was therefore not applicable for any research category.

---

## External References

> This section provides traceability from generated content back to source documents.

### Document Register

| Doc ID | Filename | Type | Source Location | Description |
|--------|----------|------|-----------------|-------------|
| LM12 | part-1-2-the-limerence-machine.md | Article | 000-global/external/ | The Limerence Machine Parts 1-2: Neuroscience of limerence and AI companion analysis |
| LM35 | part-3-5-the-limerence-machine.md | Article | 000-global/external/ | The Limerence Machine Parts 3-5: Weaponisation, DeLimerence case, and dual-use problem |

### Citations

| Citation ID | Doc ID | Page/Section | Category | Quoted Passage |
|-------------|--------|--------------|----------|----------------|
| [LM35-C1] | LM35 | Part Four | Design Decision | "Where companion AIs deepen attachment, Delimerence systematically loosens it." |
| [LM35-C3] | LM35 | Part Four | Risk Factor | "The most important design challenge is preventing users from becoming limerent toward the recovery tool itself." |
| [LM35-C5] | LM35 | Part Four | Business Requirement | "Limerence produces its most acute distress at 3am, when a therapist is not available." |
| [LM35-C11] | LM35 | Part Four | Functional Requirement | "The AI is labelled 'Tool' in the interface. It has no name, no avatar, no personality." |

### Unreferenced Documents

| Filename | Source Location | Reason |
|----------|-----------------|--------|
| *None* | — | All external documents were referenced |

---

## Spawned Knowledge

The following standalone knowledge files were created or updated from this research:

### Vendor Profiles
- `vendors/anthropic-profile.md` -- Created
- `vendors/supabase-profile.md` -- Created
- `vendors/aws-profile.md` -- Created

### Tech Notes
- `tech-notes/llm-safety-guardrails.md` -- Created
- `tech-notes/anti-dependency-architecture.md` -- Created
- `tech-notes/uk-mhra-digital-mental-health.md` -- Created

---

**Generated by**: ArcKit `/arckit:research` agent
**Generated on**: 2026-04-06
**ArcKit Version**: 4.6.3
**Project**: DeLimerence (Project 001)
**AI Model**: Claude Opus 4.6 (1M context)
