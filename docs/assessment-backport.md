# Selective Assessment Backport

## Source and Scope

- Fork base: `125d5e619905d97b519a887d5bc7332dcc448a52`.
- Upstream source: `affaan-m/ECC@b38be6a7f6350964d59328b52f0624e1d1d552d1`.
- This is a selective workflow backport, not a merge of the upstream runtime.

| Surface | Change |
| --- | --- |
| verification-loop | Upstream target acceptance states and pipeline exit-status corrections |
| search-first | Upstream tool-channel preflight and honest coverage limits |
| deep-research | Upstream untrusted-source boundary and tool drift caveat |
| security-review | Upstream strict CSP, parameterized SQL example and Zod correction |
| rules/common/agents.md | Upstream delegation completion contract, preserving this fork's roster |
| test-collaboration | Narrow adaptation of upstream test evidence governance; no newer governance dependencies |
| assessment-evidence | Fork adaptation of unified-memory evidence principles with IRIS / HealthShare PoC and handoff templates |

Canonical skills remain in `skills/`. Updated existing Codex projections and the
two new skills are also available under `.agents/skills/`. The new skills are
registered in the existing selective-install manifests: test-collaboration in
`workflow-quality`, assessment-evidence in `security`. Claude plugin installation
discovers them through its existing `./skills/` registration. No new slash command is required.

## Use

In Claude Code, request the `assessment-evidence` skill; plugin installs may expose
it as `/ecc:assessment-evidence`, while manual installs use the local skill name.
Ask it to validate the supplied finding set and preserve every original finding ID.
For test-asset inventory, request `test-collaboration`.

The skills follow the current task's authorization. Loading a skill does not
authorize connecting to a target or changing data.

- [Finding and PoC template](../skills/assessment-evidence/templates/finding.md)
- [Sanitized handoff template](../skills/assessment-evidence/templates/handoff.md)
- [Test evidence registry template](../skills/test-collaboration/templates/tests.md)

Keep actual assessment records and raw evidence in the authorized assessment
workspace or restricted store. These public templates must contain only synthetic
or sanitized examples. A failed reproduction does not establish FP; report blocked
execution, uncertainty and next access dependency explicitly.

## Compatibility and Exclusions

This backport adds guidance and templates only. It does not change package versions,
hooks, MCP configuration, agent tool permissions, or model selection.
It does not install or enable the Memory Vault runtime, automatic LLM summaries,
continuous-learning observers, GateGuard, or candidate execution.

Memory continuity uses manually reviewed sanitized records, not automatic transcript
ingestion. It adopts unreviewed evidence, source/time/environment attribution and
explicit supersession. This is not an implementation of the `ecc.memory.v1` API.

The unchanged bounty-oriented skill may exclude local-only or hardening issues;
that filtering must not remove supplied assessment findings from the register.
Use assessment-evidence for assessment adjudication.

## Validation

Run the repository's existing skill, manifest, catalog, Unicode and personal-path
validators. Check links, canonical/projection parity and template coverage.
No target-system acceptance is implied by these checks. IRIS / HealthShare runtime
validation requires the authorized assessment environment and is not part of this port.

Validation completed for this port:

- All existing surface validators passed: agents, commands, rules, skills, hooks,
  install manifests, catalog counts, Unicode safety and personal-path checks.
- Both new skills passed skill-creator frontmatter validation; new Markdown passed lint.
- Existing install-manifest, install-plan and catalog tests: 42 passed, 0 failed.
- Ten relative links, eight changed/new projection files and both install module
  registrations were checked; the Claude install plan resolves both new components.
- Independent instruction review covered missing credentials, direct-method-only
  success, stale target-version memory, original-ID preservation and PHI sanitization.

These are focused documentation and packaging checks, not a full runtime suite,
native Claude Code invocation test or IRIS / HealthShare target verification.
