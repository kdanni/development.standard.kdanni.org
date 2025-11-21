# Platform Usage Standards

This space outlines how enterprise platforms are provisioned, consumed, and monitored. Use
it to remind product teams of the enterprise-first mindset: leverage shared services
before building bespoke infrastructure, and document links to the EA Knowledge Base for
canonical process descriptions.

## Recommended Focus Areas
1. **Access management and tenant isolation** – Summarize the expectation (e.g., enforce SSO via centrally managed IdP,
   segregate customer data by tenant). Link to the platform security playbooks inside the knowledge base for detailed
   runbooks and control mappings.
2. **Provisioning workflows** – Describe the golden path automation (Terraform modules, portal forms) and the SLAs for
   fulfilling new environment requests. Include escalation steps when a team needs custom capacity.
3. **Operational stewardship** – Outline required monitoring (uptime, cost, utilization) and the cadence for reporting to the
   Architecture Governance Forum. Provide guidance for tagging resources so finance can attribute spend.
4. **Lifecycle management** – Note how platform upgrades, deprecations, and migrations are communicated. Encourage teams to
   create ADRs referencing the EA Knowledge Base when opting out of the shared platform.
