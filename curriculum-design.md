# Tiny Hermes Projects — Curriculum Design

**Status:** Draft 0.1 — for learner review  
**Date:** 2026-10-19  
**Scope:** Pedagogical design, not yet the Hermes feature inventory  
**Primary pedagogical source:** Ken Youens-Clark, *Tiny Python Projects* (Manning, 2020), especially “About this book,” Introduction, chapter organization, and recurring “Solution,” “Discussion,” and “Going further” sections.

## 1. Purpose

Create a hands-on, challenge-first curriculum for learning the **Nous Research Hermes Agent harness**. Each project must be independently achievable in **45 minutes or less**, with observable success criteria, optional progressive hints, and a reference solution that remains separate from the learner-facing challenge.

The curriculum teaches practical use of the harness rather than Python syntax for its own sake. Python is the default language for custom scripts and test helpers when code is needed. Exercises should also teach when **configuration, prompting, tool selection, or a built-in Hermes capability** is preferable to custom code.

**Not in scope for this document:** claims that any specific Hermes command, configuration field, API, or integration currently exists. Those details will be validated against versioned official Hermes documentation before the corresponding exercise is written.

## 2. What we are borrowing from *Tiny Python Projects*

The book is a **model of pedagogy**, not a technical reference for Hermes.

| Observed pattern in the book | Evidence in the book | Adaptation for Tiny Hermes Projects |
| --- | --- | --- |
| Present a concrete program to write before its solution | Typical chapter sequence: writing the program → solution → discussion → going further | Present a concrete agent task and acceptance criteria before guidance or solution |
| Supply tests as a specification | Introduction discusses test-driven development and running tests against the program | Supply executable checks and/or an evidence-based verification checklist at the outset |
| Increase complexity gradually | “About this book” roadmap moves from core structures to file handling, testing, and integrated programs | Order challenges by Hermes prerequisites and operational risk, not merely by exercise number |
| Encourage multiple valid implementations | Introduction and solution discussions emphasize that a passing solution need not match the author's | Evaluate behavior and constraints rather than prescribing one prompt or implementation |
| Discuss implementation choices after solving | Repeated “Solution” and “Discussion” sections | Keep reference solutions separate; explain trade-offs and failure modes after the attempt |
| Offer optional extensions | Repeated “Going further” sections | Add a stretch task that is explicitly outside the core 45-minute commitment |
| Favor small, repeatable programs | Book projects use reproducible CLI inputs and tests | Use small, resettable agent environments, fixtures, and clearly bounded tasks |

### Deliberate departures from the book

1. **Not strictly sequential.** The book recommends working through chapters in order. Our curriculum will have a prerequisite spine but also independent challenges, because Hermes has multiple domains and learner goals.
2. **Not all results are exact strings.** Agent behavior may be nondeterministic. Some tasks require deterministic checks, some require trace inspection or a rubric, and some require both.
3. **Operational safety matters.** Challenges involving external messages, websites, secrets, files, or automations need explicit permissions and safe defaults.
4. **Time is capped.** The book does not establish our 45-minute limit; that is a project requirement. We will break larger workflows into independently testable slices.
5. **Version-aware content.** Hermes features and interfaces may evolve; exercises must cite the official documentation version or access date used.

## 3. Learning principles

1. **Challenge first:** Show the desired outcome, starting state, constraints, and success checks before any walkthrough.
2. **Attempt before hint:** Encourage an initial independent attempt. Hints are optional and progressively more revealing.
3. **Test early, not just at the end:** The learner can run a check before implementation, see a meaningful failure, and iterate.
4. **One central skill per challenge:** A challenge may reinforce earlier skills but should introduce at most one major new Hermes concept.
5. **Prefer evidence to impression:** “The agent seemed to work” is insufficient; record what was invoked, changed, returned, or persisted.
6. **Use real workflows in small slices:** Research, documents, automation, communication, software development, data analysis, and multi-agent collaboration all belong in the curriculum.
7. **Separate learning from production:** Examples must not quietly send live messages, incur charges, delete user data, or expose credentials.
8. **Reflect after completion:** Capture surprises, errors, alternate approaches, and what to practice next.

## 4. Exercise format

Every learner-facing exercise is a Markdown file with these sections **in this order**:

1. **Title and metadata:** ID, level, target duration (≤45 minutes), core Hermes capability, prerequisites, documentation references.
2. **The challenge:** A short real-world problem stated without implementation instructions.
3. **Your objective:** What the learner will build or configure.
4. **Starting point:** Provided environment, starter files, fixture data, and any assumptions.
5. **Constraints:** What is allowed, disallowed, or must remain unchanged; privacy and cost limits.
6. **Acceptance criteria:** Observable, checkable conditions; distinguish required from optional behavior.
7. **Verify your work:** Exact test command(s) where available, plus evidence to inspect or capture.
8. **Time budget:** Suggested checkpoints totaling at most 45 minutes; these are guidance, not steps to implement.
9. **Optional hints:** Three progressive hints, initially collapsed or linked separately when the format allows.
10. **Going further:** One or two optional stretch ideas, clearly excluded from the time budget.
11. **Reflection:** Two or three short questions about why the solution works and how it could fail.

**Never include the complete reference implementation in the challenge file.** The reference solution lives under `solutions/` and is linked only as a post-attempt resource.

### Suggested 45-minute envelope

| Phase | Target |
| --- | ---: |
| Read challenge and inspect fixtures/tests | 5 min |
| Independent attempt | 20 min |
| Run tests, debug, improve | 15 min |
| Record outcome and reflection | 5 min |
| **Total** | **45 min** |

If a task cannot plausibly fit, split it into multiple exercises. Setup and credential provisioning that cannot reliably be completed within the window should be treated as prerequisites or provided via fixtures, not hidden inside the exercise estimate.

## 5. Difficulty levels

Difficulty describes the **cognitive and operational challenge**, not just the amount of code.

| Level | Expected learner behavior | Typical boundaries |
| --- | --- | --- |
| **Beginner** | Run, inspect, and make one focused change to an existing Hermes workflow | Single capability, prepared environment, explicit expected result |
| **Intermediate** | Combine a few capabilities and diagnose ordinary failures | Small integrations, files/tools, structured outputs, meaningful edge cases |
| **Advanced** | Design a workflow with state, delegation, or nontrivial failure handling | Multiple components, observability, recovery, controlled external effects |
| **Expert** | Make defensible architecture and reliability trade-offs under constraints | Security, evaluation, isolation, concurrency, reproducibility, failure injection |

An expert challenge must **still fit within 45 minutes** by operating on a small prepared system rather than requiring a production deployment.

## 6. Hints policy

Each exercise provides exactly three optional hints, preferably in a separate `hints.md` or clearly separated section:

- **Hint 1 — Direction:** Identify the concept or documentation area to investigate.
- **Hint 2 — Strategy:** Suggest a decomposition, diagnostic observation, or relevant tool.
- **Hint 3 — Near-solution:** Show a small command fragment, pseudocode, or key configuration shape **without** providing the complete finished answer.

Hints should be written after the challenge and tests, so they do not accidentally reveal the implementation before the learner attempts it. The learner may use any hint without penalty; record hint usage in the progress tracker for future curriculum tuning.

## 7. Verification and testing

### 7.1 Three verification modes

| Mode | Suitable for | Evidence |
| --- | --- | --- |
| **Deterministic automated tests** | Parsing, file transformations, configuration shape, mocked tool dispatch, structured artifacts | `pytest` or script exit status; fixture diff |
| **Trace/behavior checks** | Tool selection, delegation, recovery, session flow | Recorded trace/log, named tool invocation, state change, artifact inspection |
| **Rubric-based evaluation** | Research quality, summarization, interaction quality | Scored checklist with required facts, prohibited behaviors, and cited evidence |

Prefer deterministic tests whenever possible. Do not require an LLM to produce a verbatim sentence unless exact wording is itself the skill being tested.

### 7.2 Required testing rules

- Provide a **known initial state** and a way to reset it.
- Make at least one **happy-path** and one **failure/edge-case** check where applicable.
- Use fixtures and mocks for external systems unless real integration is the explicit learning objective.
- Record whether a test is **offline**, **requires a model**, or **requires an external service**.
- Where model outputs vary, assert invariants (schema, tool calls, required facts, no side effects) rather than fragile prose matching.
- Distinguish **exercise passed** from **agent response looked plausible**.
- Do not require committing secrets, tokens, personal information, or unredacted logs.
- If a live test could create charges or external effects, require an explicit opt-in and document a safe alternative.

### 7.3 Standard completion record

For each challenge, capture: status, time spent, tests passed/failed, hint level used (0–3), one key lesson, and any documentation discrepancy. Failed attempts are useful feedback, not merely incomplete work.

## 8. Curriculum architecture

Use a **hybrid** structure:

- **Independent micro-projects (default):** Each covers one practical capability in a fresh scenario, making it easy to explore broadly.
- **Short linked sequences (selective):** Two to four exercises reuse a fixture or environment when continuity genuinely teaches persistence, delegation, debugging, or evolution.
- **No mandatory single business case:** Domains rotate among research, documents, communication, automation, data analysis, and software development.

Dependencies are explicit. A learner may skip an exercise if they can demonstrate the prerequisite skill. Avoid making early challenges re-teach basic Hermes installation or connectivity already familiar to the learner; provide a short diagnostic or optional refresher instead.

## 9. Proposed repository contract

```text
README.md                  # Project overview and how to run challenges
curriculum-design.md       # This teaching contract
curriculum.md              # Roadmap and prerequisite graph
feature-coverage.md        # Official-doc capability inventory and exercise mapping
progress.md                # Learner completion and feedback
exercises/<level>/<id>/    # challenge.md, optional hints.md, fixtures as needed
starter-code/<id>/         # Minimal editable starting materials
tests/<id>/                # Automated checks and/or verification rubric
solutions/<id>/            # Reference implementation and discussion
references/                # Source index, documentation snapshot metadata
```

The top-level directories already exist in the learner's WSL2 repository. Per-exercise subdirectories are created incrementally, not all at once.

### Exercise IDs and metadata

Use stable IDs such as `H001`, `H002`, etc. Suggested header:

```yaml
---
id: H001
title: "Example title"
level: beginner
minutes: 30
capabilities: ["pending-official-feature-id"]
prerequisites: []
verification: ["offline-tests", "trace-check"]
source_checked: "YYYY-MM-DD"
---
```

These are **curriculum metadata fields**, not Hermes configuration keys.

## 10. Hermes documentation and feature coverage rules

Before authoring a feature-specific challenge:

1. Consult **official Hermes documentation** and, where necessary, the official source repository.
2. Record the source URL, access date, relevant section, and the version/commit when identifiable.
3. Give each documented capability a stable inventory ID and status: **not planned**, **planned**, **drafted**, **tested**, or **needs revalidation**.
4. Map each capability to at least one exercise and one observable acceptance check, or document why it is excluded.
5. Separate **documented behavior** from **curriculum design assumptions** and **experimental observations**.
6. Revalidate commands, flags, paths, and configuration keys before publishing a challenge.

Initial authority targets (to be checked during the inventory phase):

- Official documentation: <https://hermes-agent.nousresearch.com/docs>
- Official repository: <https://github.com/NousResearch/hermes-agent>

Do not invent a command or configuration key to make a pedagogical example look complete.

## 11. Reference solution policy

A reference solution should contain:

- A **minimal passing implementation** or configuration.
- How to run it and the expected verification evidence.
- Why it works, tied to the documented Hermes behavior.
- At least one **alternative approach or trade-off** where useful.
- A **failure analysis**: what commonly goes wrong and how to recognize it.
- Safety, cleanup, and reset instructions where relevant.

Solutions are not canonical: a learner's different implementation is acceptable if it satisfies the constraints and tests.

## 12. Quality gate for publishing an exercise

An exercise is publishable only if all answers are **yes**:

- [ ] The challenge is understandable without reading its solution.
- [ ] The new concept and prerequisites are explicit.
- [ ] The core work can reasonably finish within 45 minutes.
- [ ] The environment, fixtures, and reset procedure are available.
- [ ] Acceptance criteria are observable and non-ambiguous.
- [ ] Verification instructions work in the intended environment (WSL2 Ubuntu unless otherwise specified).
- [ ] Stochastic behavior is evaluated robustly.
- [ ] Hints progress without revealing the full solution.
- [ ] The reference solution is separate and independently verified.
- [ ] Official Hermes sources support all feature-specific instructions.
- [ ] External effects, costs, and secrets are handled safely.
- [ ] The coverage matrix and roadmap are updated.

## 13. Development and review cycle

1. **Design:** Inventory official features and choose a small pilot covering distinct capabilities.
2. **Draft:** Write challenges and acceptance checks **before** reference solutions.
3. **Validate:** Run tests against the starter state (expected failure) and reference solution (expected success), where feasible.
4. **Pilot:** Learner completes a small batch; record elapsed time, hints used, confusion, and failed checks.
5. **Revise:** Split oversized tasks, repair ambiguous criteria, and correct documentation drift.
6. **Expand:** Add exercises only after the design and test format prove useful.

**Initial pilot recommendation:** 4–6 challenges across at least three practical domains and two difficulty levels. The exact topics and total curriculum size should be decided **after** the official feature inventory; any earlier exercise count is provisional.

## 14. Open decisions for learner review

1. Should hints be in separate files (`hints.md`) or at the bottom of each `challenge.md`? **Default:** separate files for less accidental exposure.
2. Should the learner submit a short Markdown completion note per exercise or update only `progress.md`? **Default:** progress tracker plus optional notes.
3. Which tests may call a paid model or live service? **Default:** offline by default; live tests clearly labeled and opt-in.
4. Should the first pilot emphasize capabilities the learner has *not* already used? **Default:** yes, with a brief diagnostic for familiar basics.

## 15. Next deliverables

1. `references/hermes-source-index.md` — official source URLs, dates, and version notes.
2. `feature-coverage.md` — complete documented feature inventory, grouped by capability, with evidence and status.
3. `curriculum.md` — exercise roadmap and prerequisite mapping.
4. First pilot exercises, starter files, tests, and separate solutions.

---

### Source note

**Book-derived observations** in section 2 are based on the uploaded *Tiny Python Projects* PDF, especially its “About this book” roadmap and repeated chapter layout. **Design decisions** throughout this document (45-minute limit, difficulty levels, hybrid exercise architecture, agent-specific evaluation, WSL2 repository layout, and documentation-tracking policy) are adaptations for this project, not claims made by the book. Hermes-specific implementation details remain intentionally unverified until the next research phase.
