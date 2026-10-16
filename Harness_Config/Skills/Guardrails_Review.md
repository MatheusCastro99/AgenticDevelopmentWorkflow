# Guardrails Review

## What this file is for

It documents the `guardrails-review` skill: the project's own review checklist.

A reviewer with no project context reviews against generic taste. This skill gives the reviewer the project's rules to check, the mistakes that have already happened, and the limits of what can be verified from a session. It is the one checklist for reviewing a change, weighing a design, and deciding what to do with tech debt.

Both source projects call this skill `review-guardrails`. The template names it `guardrails-review`.

## What goes in it, and what stays out

Goes in the skill:

- Procedure: which documents to load before judging anything
- Checks, grouped by area, each tied to the standing rules it enforces by their IDs
- Known regression traps: mistakes that have already happened in the project
- Verification limits: what can be built and tested from the session, and what only the owner can check
- A severity scale and an output format for inline use

Stays out:

- **The rules themselves.** A skill holds procedure, not project truth. The rules live in the decisions file and the other context documents; the skill tells its reader to load them. When a check and a document disagree, the document wins and the skill gets fixed.
- **Authority.** The skill recommends; the owner decides, including the status of a standing rule.
- The scoring of the independent review. The red-team agent has its own, described in [Red Team](../Agents/Red_Team.md).

## When to use it

- Reviewing a branch, a diff or a pull request
- Evaluating a design or a refactor before it is built
- Deciding whether a piece of tech debt is fixed now, scheduled or accepted

It runs in two ways:

| How | Who loads it | Sections that apply |
|---|---|---|
| Inline | The main session. Claude Code loads a skill when its description matches the task, or on demand with `/guardrails-review`. | All six |
| Preloaded | The red-team agent, through the `skills:` field in its frontmatter | 1 to 4. The agent uses its own scoring and output in place of 5 and 6. |

## What it checks

| Section | What it holds |
|---|---|
| 1. Load the rules first | The documents to read, and how to treat a rule that is not in force yet: the gap is not a defect unless the change claims to close it |
| 2. Project checks | One block per area. Each check is confirmed with `file:line` evidence, not from memory. A last block lists the patterns the project leaves out on purpose, so that their absence is not reported. |
| 3. Known regression traps | Each trap, with the input or change that triggers it |
| 4. Verification you can do | The build and test commands, what the owner verifies by hand, and the edge cases that pass would miss. Ordinary paths the owner already covers are not listed as "needs testing". |
| 5. Severity scale | Critical, Major, Minor and Accepted trade-off, each with examples from the project and an action |
| 6. Output | A verdict, the findings most severe first, the verification results, edge cases for a manual check, and the docs the change made stale |

## Keeping it current

- When a standing rule is added or changes status, its check in section 2 is updated as part of the same change.
- When a known bug is fixed, its trap is removed.
- When a new trap is found, it is added with the input that triggers it.

## How the two projects differ

| | BabyBuddyHelper | InvoiceMe |
|---|---|---|
| Documents loaded first | The decisions file, the context index and the current-state page | The decisions file, and the issue under review with its parent epic |
| Rules not in force yet | The gap is not a defect unless the change claims to close it | The same, and a change that moves the code further from the rule is a finding |
| Traps | Listed as known regression traps | Each one was reproduced against the running API before it was listed |

On the first row the template follows BabyBuddyHelper: it loads the decisions file, the context index and the current-focus page. It keeps both sentences about rules not in force yet.

Both source skills keep the traps as a subsection of the project checks, so their severity scale and output are sections 4 and 5. The template gives the traps their own section, which makes them 5 and 6.

## Skeleton

The copy-ready skill is [Templates/skills/guardrails-review/SKILL.md](../../Templates/skills/guardrails-review/SKILL.md). Copy it to `.claude/skills/guardrails-review/SKILL.md`, fill the placeholders listed in its opening comment, and delete that comment.

| Placeholders | What they hold |
|---|---|
| `<project>` | The project's name |
| `<decisions-doc>`, `<context-index>`, `<current-focus-doc>` | The paths of the documents the skill loads |
| `<area>`, `<rule-ids>`, `<check>` | One block per group of checks |
| `<patterns-not-used>` | What the project leaves out on purpose |
| `<trap>`, `<trigger>` | One line per known regression trap |
| `<build-command>`, `<test-command>`, `<test-coverage>`, `<manual-pass>`, `<edge-cases>` | The verification limits |
| `<critical-examples>`, `<major-examples>`, `<minor-examples>`, `<accepted-trade-offs>` | The examples in the severity scale |

A check names where to look and cites its rule by ID. It does not copy the rule's text.

## Examples

Examples: [BabyBuddyHelper](../../Examples/BabyBuddyHelper-examples.md#guardrails-review), [InvoiceMe](../../Examples/InvoiceMe-examples.md#guardrails-review).
