# System Integration Standards

Use this folder to describe integration patterns, data contracts, and interoperability requirements.
Keep the guidance high-level and point to the Integration section of the EA Knowledge Base
for canonical policies and capability maps.

## Recommended Focus Areas
1. **Pattern selection** – Document when to prefer API-led, event-driven, or file-based integrations along with the
   decision criteria (latency, coupling, data volume). Reference the knowledge-base matrix for detailed pros/cons.
2. **Contract hygiene** – State expectations for schema management, semantic versioning, and backward compatibility.
   Link to shared schema registries or API catalog entries instead of duplicating payload definitions.
3. **Security and observability** – Reinforce enterprise authentication patterns (OAuth, mTLS) and the requirement to emit
   trace IDs across boundaries. Point to the centralized audit logging guidance maintained by Enterprise Architecture.
4. **Testing across environments** – Describe expectations for sandbox tenants, synthetic data, and contract-testing pipelines
   so that breaking changes are caught before promotion.
5. **Change governance** – Encourage early notification through the Integration Review Forum, capturing meeting notes that link
   back to EA Knowledge Base references for posterity.
