# Security audit triage — 2026-10-21

Parent: https://github.com/Mike-Demo/ResumeSkills/issues/1

## Prioritized backlog

The audit used static source inspection only: no code was executed and no deployed endpoint was probed.

- **Confirmed findings: 0.** There are no remediation issues to file, risk rankings to assign, or confirmed root causes to group.
- **Needs-validation leads: 2.** File the single checklist issue below. Listing order follows the parent issue, not a severity or risk ranking; neither lead has a severity. The claimed root causes are distinct and remain unconfirmed.
- **Rejected candidates: 2.** Do not reopen `estimated-metrics-presented-as-factual-resume-claims` or `reference-personal-contact-details-distributed-beyond-consent-scope` without new evidence.

Issue creation is unavailable in this session, so the exact title and body below are ready to file in this repository. No remediation or runtime validation has been performed.

## Issue title

`[security][needs-validation] Audit leads to validate`

## Issue body

Parent audit: https://github.com/Mike-Demo/ResumeSkills/issues/1

Validate both leads from the 2026-10-21 static audit. These are not confirmed vulnerabilities and have no assigned severity. Record the external tool/host version, configuration, evidence, and disposition for each lead before considering remediation.

The missing-fact text below is quoted exactly from the parent issue, including its truncated endings (`an…` and `target-controlle…`). Obtain any omitted wording from the audit owner rather than inferring it.

- [ ] **Recommended install pulls globally auto-loaded agent instructions, unpinned, from a differently-owned repo than this one**
  - Fingerprint: `unpinned-cross-owner-global-skill-install-without-integrity-binding`
  - Claimed root cause: The recommended install path is unpinned and unbound in-repo: it pulls globally auto-loaded agent instructions from a differently-owned repository with no commit, tag, or integrity binding to the source the user reviewed.
  - Repository context: `README.md`, under “Option 1: CLI Install (Recommended),” recommends `npx skills add Paramchoudhary/ResumeSkills -g -y`, while the audited repository is `Mike-Demo/ResumeSkills`. This alone does not establish the external CLI's integrity or update behavior.
  - Exact missing fact:

    > Whether the external skills CLI (npx skills add) records/pins the resolved commit at install, verifies content or warns on owner/repo mismatch, and whether an existing global install auto-updates from the upstream default branch or only changes on an explicit user re-install/update - behavior of an external tool not contained in this repository an…

  - Validation record: Document the CLI's resolved-commit persistence, integrity/owner checks, and existing-global-install update behavior, supported by external implementation/documentation or authorized isolated validation. Record whether the lead is confirmed, rejected, or still unresolved.

- [ ] **Skills direct the agent to ingest/fetch third-party job and company content with no untrusted-content boundary**
  - Fingerprint: `untrusted-job-content-enters-agent-context-without-injection-boundary`
  - Claimed root cause: Third-party job and company text enters the agent context with no in-repo instruction-hierarchy boundary directing the agent to treat it strictly as data and never follow instructions embedded in it.
  - Repository context: The parent audit identifies third-party job/company content ingestion as the entry point. Whether it can influence privileged actions depends on the consuming harness; static repository inspection does not establish that behavior.
  - Exact missing fact:

    > Whether the consuming agent harness (e.g. Claude Code or another skills host) isolates fetched/pasted third-party content from instructions, and what file/shell/credential-adjacent tools and model authority it grants while these skills run - a harness/runtime fact not present in this repository and not observable without executing target-controlle…

  - Validation record: Identify the consuming host and its configuration; document content isolation, available tools, permissions, approval gates, and model authority using host implementation/documentation or authorized isolated validation. Record whether the lead is confirmed, rejected, or still unresolved.

### Completion criteria

For each lead, attach evidence answering its missing fact or explicitly record what remains unknown. Do not mark an unresolved lead as confirmed. Only if new evidence confirms a vulnerability, create a separate remediation issue linked to this checklist and the parent audit, with evidence, established root cause, smallest safe fix, and severity based on demonstrated reachability and impact. Rank any confirmed findings by real-world risk first, then fix size/safety, grouping shared root causes.

The previously rejected candidates `estimated-metrics-presented-as-factual-resume-claims` and `reference-personal-contact-details-distributed-beyond-consent-scope` remain excluded unless new evidence warrants reconsideration.
