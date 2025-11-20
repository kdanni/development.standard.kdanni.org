# Dependency Management and Supply Chain Security Standard

## Purpose
Define engineering requirements to ensure dependencies, build artifacts, and repository infrastructure are trustworthy, reproducible, and lifecycle-managed across all services.

## Applicability
This standard applies to all software and infrastructure repositories, CI/CD pipelines, and artifact distribution mechanisms used by the organization.

## Version Management
- Pin exact versions for direct dependencies in manifests and lockfiles; disallow semver ranges in production builds.
- Lock transitive dependencies via reproducible lockfiles or checksum manifests; refresh lockfiles quarterly to capture security fixes.
- Enforce deterministic builds by storing build container digests (not tags) and verifying digest consistency on every pipeline run.

## Lifecycle Management
- Maintain a dependency inventory that tracks support windows and end-of-life dates.
- Initiate deprecation when a dependency reaches six months from end-of-life. Publish migration guidance and timelines in the repository README or docs.
- Upgrade cadence: critical security updates within 14 days; high severity within 30 days; routine updates at least quarterly.
- Remove or replace deprecated dependencies no later than one release before their published end-of-life date.

## Conflict Handling
- Configure package managers to fail on version conflicts rather than auto-resolving to the newest version.
- Document chosen resolutions (e.g., `resolutions` blocks, exclusion rules, or module replacements) in version control alongside rationale.
- Add regression tests or contract tests that cover the impacted dependency surface before merging conflict resolutions.

## Third-Party Dependency Intake
- Evaluate new dependencies for maintainer activity, release signing, vulnerability history, and license compatibility prior to adoption.
- Require SBOM generation on every build; publish SBOM artifacts with releases and store them for audit.
- Only use dependencies available from approved, authenticated repositories or organization mirrors.

## Repository and Build Infrastructure
- All package registries, artifact stores, and container registries must enforce TLS, MFA for publishers, and signed artifacts (Sigstore, Notary, or GPG).
- Configure CI/CD runners to operate in isolated networks with egress restricted to approved mirrors. Disallow direct access to public registries from production pipelines.
- Enable tamper-evident logging for build and publish steps; retain logs for a minimum of one year.
- Back up repository metadata and signing keys, storing recovery materials in hardware-backed vaults with dual control.

## Active Supply Chain Threat Mitigation
- Subscribe CI/CD to dependency confusion and typosquatting protections (namespace reservation, scoped registries, hash verification).
- Validate checksum and signature for every downloaded dependency and base image; fail builds on mismatch.
- Implement quarantine workflows for suspected malicious packages: blocklist in mirrors, purge caches, and run forensic scans before re-enabling.

## Legal and Compliance Controls
- Record license terms for every dependency in the SBOM and track obligations (notice, copyleft, export restrictions).
- Obtain Legal/Compliance approval before introducing dependencies with non-standard or viral licenses; document approvals in the repository.
- Maintain supplier contracts for private repositories requiring: breach notification, signing commitments, uptime SLAs, and indemnification where feasible.

## Governance and Evidence
- Add CI checks that verify lockfile freshness (age < 90 days), presence of SBOM artifacts, and signature verification results.
- Run automated SCA on every pull request and nightly on main branches; fail pipelines on unapproved critical/high findings.
- Archive evidence (SBOMs, scan reports, signature verification logs, exception approvals) with release artifacts for audit readiness.

## Exceptions
- Exceptions must include scope, duration (≤90 days), compensating controls, and approval from Security Engineering. Legal/Compliance approval is required when licensing is affected.
- Track exceptions in repository documentation and review monthly until closed.
