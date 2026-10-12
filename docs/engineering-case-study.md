# Engineering case study

## Problem

The initial ambition was to hand a development objective to an AI system and return later to a verifiable result. The first engineering problem was more basic: an agent could finish a process and say “done” without proving that it respected the permitted files, executed meaningful checks, or left the environment safe.

BAHAO therefore focused on a constrained acceptance workflow. A task would be accepted only after the proposed change, executed verification, independent review, and final cleanup agreed on the same task and candidate. **[E2–E4; source register in verification.md]**

## Constraints

The prototype operated on Windows, used a fixed C# target and verification plan, and had to protect the controller from code that had not yet been reviewed. Existing governance behavior was frozen rather than repeatedly redesigned. Deployment also crossed packaged desktop and ordinary Windows process contexts.

The Owner required explicit permission boundaries, bounded work, evidence preservation, and a stop when a result could not be trusted. These were product requirements directed by the Owner; implementation and debugging were AI-assisted. The Owner's contribution was not a claim of independently hand-writing every process, filesystem, or recovery primitive. **[E7]**

## Design decisions

**Separate completion from acceptance.** The Executor proposes a change. The Supervisor checks scope, builds a candidate, runs verification, and validates an independent review before publishing success. Neither an exit code nor a model's final message can authorize acceptance. **[E3, E4]**

**Protect the controller before running candidate code.** Builds and tests can execute code. They therefore belong inside the candidate execution boundary, even though they happen before the final Reviewer decision. Job containment, restricted execution, protected inputs, and permission checks address different parts of this boundary. **[E4]**

**Treat recovery as part of the protocol.** Resource ownership must survive the Supervisor. A later trusted process needs enough recorded identity to distinguish the operation's permission changes from somebody else's legitimate state. Restoring the environment must not silently resume a failed task. **[E4]**

**Keep the caller adapter thin.** The Launcher submits work and projects a validated Core checkpoint. It does not reimplement review or turn a transport exit code into a successful task. **[E5]**

## Implementation

AI tools contributed implementation and investigation across PowerShell orchestration, Windows process and permission boundaries, C# fixtures, and the Launcher. The Owner defined the workflow and acceptance gates, organized implementation and independent review rounds, constrained authorized changes, and decided when evidence justified progression or a stop. **[E7]**

The resulting flow tied the Task Contract to one execution and one candidate commit. Source and generated runtime manifests guarded later phase inputs. Actual phase output entered the evidence chain. The Reviewer received a prepared evidence bundle in a fresh read-only session, and the Supervisor checked its result and bindings before committing the verdict. **[E3, E4]**

## Validation

The final Core smoke and later Launcher demonstration used real Codex sessions. The Launcher demonstration added one harmless comment in the authorized file, completed build and designated audit/diagnosis phases, passed GameCore 248/248 and Simulator 67/67, received independent Reviewer `PASS`, and returned the Core's authoritative production `PASSED` to the caller. Cleanup was recorded for that run. **[E2, E3]**

The distinction matters: these were 315 target-project tests and a constrained integration demonstration. They did not establish general feature-development ability or complete safety. The broader archived regression retained 12 failures, classified in its release record as known test issues. The historical delta review also retained conditions and known risks. This portfolio reports those facts rather than replacing them with an “all tests passed” claim. **[E6]**

## Failure analysis

### Filesystem visibility across Windows hosts

Historical handoff notes describe working-directory failures, including error 267, around MSIX filesystem virtualization. The preserved external-host evidence establishes the successful resolution used for release: a verified ordinary Windows host, physical file identity, and a real Codex working-directory probe that could read, edit, and inspect the intended disposable workspace. The original error trace is not distributed or independently reconstructed in this portfolio. **[E2, E8]**

**Lesson:** a familiar path string does not prove that another process sees the same object. Validate the environment in which the actual child will run.

### Unreviewed code and trusted records

Scope instructions in a prompt do not protect state, journals, or verification tools. The implementation separated the Executor's workspace and candidate execution from trusted records, then checked both actual changes and the inputs consumed by later phases. **[E4]**

**Lesson:** write protection and after-the-fact validation complement each other. Neither should be described as a substitute for the other.

### Crash recovery and shared resources

The recovery design moved ownership out of Supervisor memory and into a protected durable record. Recovery checks object identity and attributable permission changes before acting. The successful demo records normal cleanup; that is not proof of every crash scenario. **[E3, E4]**

**Lesson:** the clean ending of one run does not validate every interrupted state. Keep normal cleanup, compensation, and unresolved conflict visible as separate outcomes.

### Successful build, insufficient review evidence

An earlier Launcher run built and tested successfully but returned `WAIT_OWNER` after Reviewer `ESCALATE`: required build evidence had been excerpted. The fixed evidence input limit remained in place. The successful later demonstration used the previously validated target baseline and had full required build objects within the limit; it did not solve large-evidence support. **[E3, E5]**

**Lesson:** preserve an honest refusal when the evidence cannot support acceptance. Making the output look successful would remove the purpose of the gate.

### Successful Core, unreliable transport completion

The Launcher evolved to validate a durable Core checkpoint and write a caller-side projection. Its source of truth is the committed task result, not the presence of a host output file or a process exit code. The final demonstration records a validated caller `PASS`; it does not establish the exact cause of every historical host termination. **[E3, E5]**

**Lesson:** execution success and delivery of that result are separate engineering responsibilities.

## Lessons learned and the decision to stop

The prototype answered a narrow question: a real agent's constrained change could pass through controlled execution, verifiable evidence, independent review, cleanup, and an authoritative caller result. **[E2, E3]**

It also exposed the cost of generalization. Task acceptance, generated runtime inputs, build/test selection, and diagnostic evidence were tightly coupled to one C# project. Extending that into arbitrary multi-file work would require further interface and verification design. **[E4, E7]**

The Owner chose to archive the working prototype and evaluate existing native Codex capabilities instead of continuing toward a new general-purpose agent platform. That was an opportunity-cost decision, not a claim that all broader requirements had been solved. **[E7]**

For a future project, the first milestone would be a small task/evidence interface validated against several representative task shapes before investing heavily in orchestration. Existing agent capabilities would be assessed first. This is a lesson and proposed approach, not a feature implemented in BAHAO.

Source labels resolve in [verification](verification.md#evidence-register). Owner-contribution and archival decisions are Owner-provided context, identified separately from runtime evidence.
