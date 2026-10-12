# Verification and evidence limits

This is a sanitized summary of preserved local artifacts, inspected during portfolio preparation on **12 October 2026**. No Executor, smoke, regression suite, or security review was rerun for this document. Private paths, usernames, session identifiers, raw logs, security configuration, and source code are omitted.

The original artifacts and a claim-to-source map remain outside this repository. The public summaries provide a bounded account of the evidence; they do not let a reader independently reproduce or audit the private implementation.

## Frozen identity

| Field | Value |
| --- | --- |
| Release | `BAHAO-Core-1.0-V2.2-Stable` |
| Controller commit | `1710a0b1fb94ec7750e0d7ea95449b47b1845d7e` |
| Validated patch-content manifest SHA-256 | `66EA53ED68E8F38AFF153127A28E4291F2D8A5E4A8CB0299230665C1EAAD4914` |
| Canonical committed diff SHA-256 | `5336CF4D9CF84A94E15C7809F70D30D1FF453440F5AD2440ED0515782AD8B50F` |

The two SHA-256 values identify different byte sequences: the validated content manifest and the canonical Git diff. They must not be treated as interchangeable. The ten files in the committed-content manifest were checked against their recorded hashes and lengths during portfolio preparation. **[E1]**

## Evidence register

These labels are public aliases for local sources, not links to published raw artifacts.

| ID | Source | What it supports |
| --- | --- | --- |
| E1 | Freeze record and committed-content manifest, 7 October 2026 | Release identity and exact frozen content |
| E2 | Final external-host smoke report, acceptance observation, host and working-directory probe | Real execution/review, designated phase results, physical deployment, and run-specific cleanup |
| E3 | Successful Launcher E2E verification, Core checkpoint, Executor/scope results, review packet/input/result, TRX files, caller projection, and closure record, 7 October 2026 | End-to-end acceptance of the authorized comment-only task |
| E4 | Frozen workflow documentation and bound controller source references | Implementation and intended enforcement, with coverage limits retained |
| E5 | Launcher entrypoint/projection implementation, early escalation verification, and successful E2E record | Verdict projection and evidence-coverage failure behavior |
| E6 | Frozen release evidence index, final regression classification, and historical delta security review | Broader test accounting, known gaps, and conditional review scope |
| E7 | Owner's archival brief | Personal contribution, original ambition, and decision to stop generalization; not runtime evidence |
| E8 | Historical handoff recap, corroborated by E2's successful external-host/CWD artifacts | Context for the earlier virtualization/error-267 investigation; original failure trace not reproduced here |

## Final Core smoke

The archived acceptance record reports a real Codex Executor and separate Reviewer session, one permitted comment-only change, successful build, GameCore **248/248**, Simulator **67/67**, completed audits and diagnostics, Reviewer `PASS`, and authoritative production `PASSED`. It reports zero unauthorized diff and clean resources for that smoke. **[E2]**

This smoke preceded the mechanical freeze. E1 records that the committed content matched the validated patch. The smoke's target candidate commit is separate from the frozen controller commit.

## Successful Launcher demonstration

The demonstrated task added a harmless English comment to the one permitted C# source file. The designated target baseline differed from the controller release baseline; it was the previously validated target used for the smoke. This is a constrained integration case, not a general development benchmark. **[E3]**

| Gate | Observed evidence |
| --- | --- |
| Real Executor | `COMPLETED`, exit 0, process tree reported empty |
| Scope | `ALLOWED`, one changed file, effective change, protected region verified |
| Candidate | One file with one inserted comment; starting/resulting commits bound in Task state |
| Build | Phase complete, exit 0 |
| GameCore | TRX: 248 total, 248 executed, 248 passed, 0 failed |
| Simulator | TRX: 67 total, 67 executed, 67 passed, 0 failed |
| Audit / diagnosis | Two audit and two diagnosis phases complete, exit 0 |
| Full build evidence | Execution descriptor: 5,371 bytes; build log: 3,948 bytes; both recorded as full content |
| Reviewer | `PASS`, packet/input hashes match the bound artifacts |
| Core verdict | `PASSED`; `authority=PRODUCTION`; `productionAuthoritative=true` |
| Launcher | Caller `PASS`; `projectionSource=AUTHORITATIVE_CORE_CHECKPOINT` |

The Reviewer limited its conclusion to the fixed diagnostic contract and supplied evidence. Its PASS did not establish full event-trace equivalence or production game quality.

During portfolio preparation, the packet, input, and result hashes/lengths were checked against the successful checkpoint, and both existing TRX files were read for their counters. The candidate diff summary was inspected read-only. These checks validate the preserved records; they are not a new execution of the pipeline.

### Resource closure for this demonstration

The preserved closure observation records `CURRENT_OWNER` recovery, `RECOVERED`, **296 recorded resources revoked**, zero residual ACL entries, zero active Job members as reported by that check, no remaining profile, and no live owner. The observation belongs to this demonstration only. It is not a current machine-wide resource survey or a guarantee for future runs. **[E3]**

### Launcher deterministic verification

The E2E verification record reports **5/5 hash fixtures** and **11/11 projection cases** in each of Windows PowerShell 5.1 and PowerShell 7. These are recorded historical results, not tests rerun for the portfolio. The Launcher uses in-process .NET SHA-256 for identity-critical hashing. **[E5]**

## Broader regression and security review

The frozen release index records this separate full regression. **[E6]**

| Suite | Run | Passed | Failed |
| --- | ---: | ---: | ---: |
| GameCore | 248 | 248 | 0 |
| Simulator | 67 | 67 | 0 |
| Overnight / controller tests | 230 | 218 | 12 |
| **Total** | **545** | **533** | **12** |

Skipped: 0. Incomplete: 0. Recorded wall time: 216.9 minutes.

The release classification attributes nine failures to missing fixture imports before the challenged Git action, two to deadline scenarios not reaching their intended gate in time, and one to missing child-identity telemetry after earlier rejection/cleanup assertions. It records no product blockers and clean closure. **That classification does not turn the failures into passes or prove the unexecuted scenarios.**

The historical delta security review is titled `SECURITY_PASS_WITH_KNOWN_RISKS` and covers a specific implementation delta. It also explicitly conditions progression on an acceptable final regression, including zero failures. The later archived regression has 12 failures. This portfolio reports both records and does **not** claim that the review's zero-failure condition was satisfied, that a full security audit passed unconditionally, or that later smoke success closes those coverage gaps.

The review also lists low/informational limitations in test-only replacement acknowledgement and branch coverage. Its scope and conditions must remain visible when discussing the frozen release.

## Evidence-based refusal

An earlier Launcher demonstration returned `WAIT_OWNER` with Reviewer `ESCALATE` even though its target test suites passed. Required build objects exceeded the full-input threshold and were represented as excerpts. The Reviewer correctly lacked sufficient required coverage for PASS. **[E5]**

The subsequent successful demonstration had required build objects small enough to be supplied fully. It did not increase the threshold, weaken review requirements, or establish general large-evidence support.

## What this evidence does not establish

- Quality of a substantial feature implementation: the successful change was a comment.
- General multi-file or cross-language project support.
- An all-green controller regression, complete adversarial coverage, or an unconditional security certification.
- All-day unattended operation, cross-provider orchestration, enterprise deployment, or multi-user isolation.
- The cause of every historical Windows Job or external-host failure.
- Universal cleanup behavior after every interruption or machine power loss.

For product boundaries, see [limitations](limitations.md). For implementation responsibilities, see [architecture](architecture.md).
