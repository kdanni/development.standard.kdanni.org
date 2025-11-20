# Supply Chain Security and Dependency Management Policy

## Policy Statement
All software delivered by the organization must follow verifiable supply chain security controls and disciplined dependency management. The policy requires teams to continuously manage versions, lifecycle, and provenance of all third-party and internal components to prevent integrity loss, security compromise, and legal exposure.

## Scope
- Applies to all application code, infrastructure-as-code, container images, and CI/CD pipelines managed by the organization.
- Covers third-party libraries, container base images, build tooling, package repositories (public or private), and any service used to compile, build, or distribute artifacts.

## Roles and Responsibilities
- **Engineering Teams** – Implement standards in repos and pipelines, maintain dependency manifests, execute upgrades, and document exceptions.
- **Security Engineering** – Owns tooling (scanners, SBOM generators, integrity verification), monitors for active supply chain attacks, and approves exceptions.
- **Release Managers** – Enforce gates before promotion and keep records of provenance, approvals, and exception expirations.
- **Legal/Compliance** – Reviews licensing and contractual obligations for third-party dependencies and repositories.

## Core Controls
1. **Precise version management** – All dependencies must use explicit, immutable version pins. Floating ranges are prohibited in production. Build pipelines must verify the resolved versions match SBOM expectations and artifact locks.
2. **Lifecycle governance** – Maintain an inventory that includes support status and end-of-life dates. Deprecate dependencies with less than six months of support remaining and complete upgrades at least one release before end-of-life.
3. **Conflict handling** – Dependency resolution must fail closed on conflicts. Teams must document resolution strategies (preferred transitive versions, overrides, or component removal) and capture them in lockfiles and changelogs.
4. **Repository integrity** – Only approved repositories (artifact, package, container registries) may be used. All must enforce TLS, MFA for maintainers, and signing for published artifacts.
5. **Provenance and attestation** – CI/CD pipelines must generate SBOMs, verify signatures for fetched artifacts, and produce attestations for build steps and promotion events.
6. **Change control** – Dependency and tooling changes follow the [Change Management Policy](change-management-policy.md) and require code review plus automated testing.

## Third-Party Dependencies
- Perform security scanning (SCA, vulnerability feeds) on every merge to main and on a scheduled weekly run; block promotion on critical/high issues without approved exceptions.
- Record license type and obligations in dependency manifests. Block usage of copyleft or restricted licenses unless approved by Legal/Compliance.
- Prefer well-supported dependencies (active maintainers, signed releases, security advisories). Replace abandoned components within one quarter of identification.

## Third-Party Repository Infrastructure
- Use organization-managed mirrors or proxies for public repositories. Direct access to the public internet during builds must be blocked unless explicitly approved.
- Require signed metadata (e.g., TUF/Notary) where available. For repositories lacking signing, cache artifacts in vetted internal stores and checksum them on retrieval.
- Maintain access control lists for repository admins and publishers. Review access quarterly and rotate publishing credentials at least every 90 days.

## Active Supply Chain Attack Response
- Security Engineering monitors upstream advisories, typosquatting alerts, and abnormal dependency diff signals. Engineering teams must respond to alerts within two business days.
- Invalidate affected artifacts through revocation in package registries and purge caches. Require re-builds from known-good sources after validation.
- For compromised repositories or tooling, pause releases, switch to vetted mirrors/backups, and perform forensic logging review before resuming.

## Legal Liability and Compliance
- Maintain evidence of license reviews, SBOMs, and signature verification to demonstrate due diligence.
- For third-party repositories and vendors, ensure contracts include breach notification, code signing, and tamper-evidence obligations. Vendors without contractual security commitments require a documented risk acceptance signed by Legal/Compliance.

## Exception Handling
- Exceptions must specify scope, duration (maximum 90 days), compensating controls, and approval from Security Engineering and Legal/Compliance when licensing is impacted.
- Exceptions are tracked in repository documentation and reviewed at least monthly.

## Enforcement
- CI/CD gates block merges or promotions when version pins, SBOM generation, signing verification, or vulnerability thresholds fail.
- Quarterly audits sample dependency manifests, repository configurations, and exception logs. Repeated violations may trigger freeze of deployments until remediation plans are approved.

## Related Documents
- [Secure Release Policy](secure-release-policy.md)
- [Change Management Policy](change-management-policy.md)
- [Performance and Scalability Standard](../standards/performance-and-scalability-standard.md)
