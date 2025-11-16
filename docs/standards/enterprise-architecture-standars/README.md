# Enterprise Architecture Standards

This directory documents portfolio-level standards, aligning systems, platforms, and integration patterns with enterprise goals.
The intent is to provide **mindset-setting recommendations** that help engineering teams reason about enterprise alignment.
Canonical requirements, architecture principles, and capability maps live in the Enterprise Architecture Knowledge Base
repository (`enterprise-architecture/knowledge-base`). Each document in this folder should link to the relevant knowledge-base
section rather than restating those requirements.

## Scope of the Recommendations
- Define governance roles and escalation paths for architecture decisions, with references to the EA Knowledge Base entries for
  RACI charts and engagement models.
- Map relationships between business capabilities and supporting systems at a high level so engineers can navigate to the
  detailed capability models in the EA Knowledge Base.
- Capture technology lifecycle expectations (adopt, tolerate, deprecate) and point to the authoritative technology radar or
  platform scorecards stored in the knowledge base.
- Reinforce mindset cues: favor composable platforms, document bounded contexts, and consider enterprise reuse before building
  net-new services.

## How to Use These Standards
1. Start every initiative by reviewing the matching capability or platform entry in the EA Knowledge Base; link those references
   in your design docs.
2. Treat the recommendations here as prompts for discovery conversations with Enterprise Architects rather than a checklist of
   mandates.
3. Record any deviations plus the rationale in your ADRs so portfolio reviews can trace local decisions back to enterprise
   considerations.
