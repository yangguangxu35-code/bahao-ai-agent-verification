# Known limitations

BAHAO is archived as a constrained execution and verification prototype. Its frozen status preserves a known implementation; it does not imply general availability or complete security assurance. Sources are listed in [verification](verification.md#evidence-register).

## Task and verification scope

- **Restricted single-file support.** The demonstrated task changes one designated C# source file. A permitted comment insertion is not evidence of general feature delivery.
- **Fixed acceptance assertion.** The validated interface includes a fixed text-presence check in addition to scope, build/tests, diagnostics, and review. This is not a general acceptance language.
- **Hard-coded C# verification.** Project selection, build/test steps, runtime manifests, and diagnostic expectations are tied to the target solution.
- **No general-purpose multi-file development.** Broadening scope requires new design and validation; it is not a configuration-only capability demonstrated here.
- **No validated all-day unattended work.** A successful bounded task does not prove a day-long mission, queue, or sustained autonomous planning.
- **No Claude Code or Gemini execution adapters.** The validated Executor and independent Reviewer use Codex. There is no validated parallel coding team or automatic provider routing.
- **Executable automatic repair remains disabled.** Review findings do not authorize an uncontrolled repair loop. Owner-action outcomes remain meaningful.

## Evidence and review limits

Required evidence above **65,536 bytes** may be excerpted by the frozen input collector. Where full coverage is required and no accepted deterministic coverage is available, this can cause `ESCALATE` / `WAIT_OWNER`. A successful build does not override that requirement. **[E4, E5]**

The Reviewer reasons over supplied evidence; it does not independently run commands against the workspace. Fixed deterministic summaries cover their defined checks, not every exploratory metric or every possible business property. Hashes bind bytes but cannot make incomplete or incorrectly interpreted evidence sufficient. **[E3, E4]**

## Test and assurance limits

The broader frozen regression records **533/545 passes and 12 failures** classified as known test issues. Some target scenarios were not reached. The historical delta review had known risks and a zero-failure regression condition that the archived full-run counts do not satisfy. Neither the release label nor the later real smoke is presented here as closing that discrepancy. **[E6]**

Archived workflow notes retain unexplained historical Windows Job assignment failures. The successful final run does not establish their cause or a cross-environment reliability rate. No new investigation was conducted for this portfolio. **[E4]**

## Environment and recovery limits

Windows host context, toolchain, sandbox availability, and filesystem identity matter. The verified external host avoids a demonstrated deployment/context mismatch; it is not a portability guarantee. **[E2]**

Durable recovery can restore attributable resource changes at the next trusted entry or refuse ambiguous state. It does not promise immediate cleanup after power loss, silently resume failed work, or prove that every crash window has been tested. A clean recorded ending applies to the specific checked run. **[E3, E4]**

## Distribution and project status

This repository distributes explanatory documents only. It contains no production runtime, source package, private logs, host configuration, game content, or credentials. It is not an installable BAHAO release. Private provenance remains available to the Owner for controlled review; raw evidence is not automatically authorized for redistribution.

The Owner stopped expansion after the constrained prototype succeeded and the coupling of task contracts, runtime inputs, and review evidence became clear. Considering native Codex capabilities and maintenance cost, further generalization was not justified for this project. This is an archival decision, not a claim that the broader autonomous-team goal was completed. **[E7]**
