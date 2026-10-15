# Decisions and Consistency

## What this file is for

It holds the project's standing rules, written as ADRs: rules every change must follow, which a reviewer can check a change against. It is a snapshot of the rules in force today, not a log of every decision the project has made.

The main session reads it before planning or editing, so that a change follows the rules instead of rediscovering them, producing consistency and uniformity across the implementation process. The [guardrails review](../Skills/Guardrails_Review.md) skill checks a change against it by ADR number, and so does the [red-team](../Agents/Red_Team.md) agent, which preloads that skill. The [historian](../Agents/Historian.md) reports rule text that a change has made untrue.

The rules belong to the owner. The main session may propose or draft one; it does not add, reword, or change its status on its own ([Working Agreements](Working_Agreements.md), "Who decides").

## What goes in it, and what stays out

Goes in:

- A rule every future change must follow: one source of truth for each kind of data, one fixed path for every request, records found by Id and never by reference, where secrets are kept
- The reason for each rule, so that a reader can tell when a change breaks its intent and not only its wording
- A deferral, when it constrains future work: for example, no architecture pattern until the project's complexity justifies one

Stays out. None of these is an ADR:

- One-off choices, such as a library picked for one task or the plan for one migration. Those go in the issue, the pull request or the commit message.
- The story of how a decision was reached. That is a comment on the issue ([Working Agreements](Working_Agreements.md), "Where decisions are recorded").
- Facts that go stale with the next change, such as line numbers or counts. The structure and the key files belong with the architecture document.
- How the owner and the agent work together. That is in [Working Agreements](Working_Agreements.md).
- Rules about how the main session behaves in the repository. They are in the agent's guidance file.

## The ADR format

Each rule is one block:

| Part | What to write |
|---|---|
| Heading | `ADR-` and a number: `ADR-001`, `ADR-002`, … |
| Rule | The rule, stated in the present tense |
| `Reason:` | Bullets: why the rule exists, or what goes wrong without it |
| Optional | `Rules:` for the sub-rules a reviewer checks, `Examples:` for where the rule applies, or a link to the diagram that draws it |
| `Status:` | One of the three statuses below |

| Status | Meaning |
|---|---|
| `Accepted, current` | In force now. Expected to change as the project grows. |
| `Accepted, permanent` | In force, and not expected to change. |
| `Accepted, pending (<what it waits for>)` | Decided, not in force yet. The code may not follow it until the named work lands. |

- The owner changes a status, and only after checking the work that brings the rule into force.
- A rule that is retired is removed from the file. Git keeps its history.
- When a rule is added or changes status, its check in the guardrails review skill is updated in the same change ([Guardrails Review](../Skills/Guardrails_Review.md), "Keeping it current").

## Skeleton

Copy the page outline, replace the text in angle brackets, and repeat the ADR block for each rule. Delete `Rules:` and `Examples:` from a rule that needs neither, and delete the comment under the status.

Placeholders: `<date>`, `<project>`, `<NNN>`, `<status>`, and the text in angle brackets in the ADR block.

```markdown
# Decisions

Last updated: <date>

The standing rules every change to <project> must follow. A one-off choice is not a rule: it goes in its issue or pull request.

### ADR-<NNN>
<The rule, in the present tense.>

Reason:
- <Why the rule exists, or what goes wrong without it.>

Rules:
- <A sub-rule a reviewer can check.>

Examples:
- <Where the rule applies.>

Status: Accepted, <status>
<!-- <status> is one of: current | permanent | pending (<what it waits for>) -->
```

## Examples

Excerpts from the decisions files of BabyBuddyHelper and InvoiceMe arrive in `Examples/` with [#7](https://github.com/MatheusCastro99/AgenticDevelopmentWorkflow/issues/7).
