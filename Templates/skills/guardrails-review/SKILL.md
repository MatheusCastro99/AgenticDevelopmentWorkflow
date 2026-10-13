---
name: guardrails-review
description: <project>'s project-specific review checklist. Covers the checks behind each standing rule, the known regression traps, the verification limits and a severity scale for findings and tech debt. Use when reviewing a diff or pull request, evaluating a design or refactor, or deciding whether tech debt should be fixed now. Preloaded by the red-team agent.
---

<!--
Template. Copy this file to `.claude/skills/guardrails-review/SKILL.md` in your project,
fill the placeholders, then delete this comment. The frontmatter must stay on line 1.

Placeholders:
- <project>              the project's name
- <decisions-doc>        path to the file that holds the standing rules
- <context-index>        path to the page an agent loads first
- <current-focus-doc>    path to the page that says what is being worked on
- <area>                 the name of a group of checks (data ownership, request path, …)
- <rule-ids>             the IDs of the standing rules that group enforces
- <check>                one thing to confirm in the code, with the file or name to look at
- <patterns-not-used>    the patterns the project leaves out on purpose
- <trap>                 a mistake that has already happened in this project, in one sentence
- <trigger>              the input or change that causes it, and what goes wrong
- <build-command>        the command that builds the project
- <test-command>         the command that runs the tests
- <test-coverage>        one or two sentences on what the tests cover and what they do not
- <manual-pass>          what the owner verifies by hand on every change
- <edge-cases>           the kinds of cases the tests and that pass would miss
- <critical-examples>    two or three examples of a Critical finding in this project
- <major-examples>       two or three examples of a Major finding
- <minor-examples>       one or two examples of a Minor finding
- <accepted-trade-offs>  what the documents say is intentional

Repeat the `### <area> (<rule-ids>)` block once per group of checks, and the trap line
once per trap. Each check names where to look; it does not copy the rule's text.
-->

# Guardrails Review

This is the checklist for judging a change against **this project's** rules rather than generic taste. It holds the procedure and the traps. The rules themselves live in the project's documents, so read those instead of trusting any restatement here.

## 1. Load the rules first

Read these before judging anything. If a check below disagrees with them, the documents win. Say so in the output so this skill can be fixed.

- `<decisions-doc>`: the standing rules and their current status
- `<context-index>`: what the project is, and its warnings
- `<current-focus-doc>`: what is being worked on, and what is intentionally unfinished

A rule whose status says it is not in force yet (pending, temporary) describes a target, not the current state. Don't report the gap as a defect unless the change under review claims to close it. A change that moves the code further from that target is a finding.

## 2. Project checks

Confirm each check with evidence from the code (`file:line`), not from memory.

### <area> (<rule-ids>)
- <check>
- <check>

### Simplicity
- The following are **not** defects: <patterns-not-used>. Recommend one only when a concrete, present problem needs it, and name that problem.
- Prefer the simplest change that fits. Speculative future-proofing is a finding in its own right.

## 3. Known regression traps

These have already happened in this project. Check the change against each one.

- **<trap>** <trigger>

## 4. Verification you can do

- Build: `<build-command>`. Report new warnings, not just errors.
- Tests: `<test-command>`. <test-coverage>
- The owner checks by hand: <manual-pass>. Don't list those paths as "needs testing". List only what the tests and that pass would miss: <edge-cases>.

## 5. Severity scale (findings and tech debt)

Sections 5 and 6 apply when this skill is used inline. The red-team agent uses its own scoring and output instead.

| Level | Meaning | Examples here | Action |
|---|---|---|---|
| **Critical** | Wrong or lost data, a crash, exposed secrets, or a broken standing rule | <critical-examples> | Fix before merge |
| **Major** | A real reliability or maintainability risk | <major-examples> | Fix before the next issue |
| **Minor** | Friction, clarity, naming | <minor-examples> | Mention; fix if cheap |
| **Accepted trade-off** | Intentional, per the documents | <accepted-trade-offs> | Don't raise it again |

## 6. Output

- **Verdict:** Approve / Approve with changes / Rework recommended
- **Findings:** list them most severe first. Each one gets a title, the evidence (`file:line`), its impact, a fix, the severity, and the rule or trap it violates.
- **Verification results**
- **Edge cases for manual check** (only the kind named in section 4)
- **Docs made stale** by the change (file and section). These go on the main session's stale-docs list.

These are recommendations. The project owner makes every decision, including the status of a standing rule.
