# Data Flow

## What this file is for

It draws the workflow as one diagram: the stages of an issue, the two subagents, and the documents that move between them. It shows what [Development Workflow](Development_Workflow.md) describes in words.

The agent reads it to see where a subagent runs and what to hand it. A reader new to the project sees the whole path of an issue at a glance.

## What goes in it, and what stays out

Goes in:

- The stages, in order
- Each subagent, at the stage where it runs, with what it receives and what it returns
- The documents a stage reads or writes: the issue, the context documents, the stale-docs list, the pull request, the project documentation

Stays out:

- What happens inside a stage. That is in [Development Workflow](Development_Workflow.md).
- The owner's approval at the end of each stage. It applies to every stage, so drawing it thirteen times would hide the rest.
- The project's own runtime data flow (requests, storage, screens). That belongs with the architecture document.

## The diagram

Boxes are stages, rounded shapes are subagents, and slanted shapes are documents. The owner approves the end of every stage; see [Working Agreements](Working_Agreements.md).

```mermaid
flowchart TD
    ISSUE[/"Issue and its comments"/]
    CTX[/"Context documents"/]
    LIST[/"Stale-docs list"/]
    PR[/"Pull request"/]
    DOCS[/"Project documentation"/]
    NOTES[/"Agent's persistent notes"/]

    RT(["red-team subagent"])
    HI(["historian subagent"])

    S1["1. Gather all relevant information"]
    S2["2. Settle open questions and decisions"]
    S3["3. Plan the issue's sub-phases"]
    S4["4. Plan the implementation of each phase"]
    S5["5. Implement"]
    S6["6. Test and refine"]
    S7["7. Open a pull request"]
    S8["8. Monitor CI and comments"]
    S9["9. Last pass and red-team scan"]
    S10["10. Fix comments and findings"]
    S11["11. Historian doc pass"]
    S12["12. Ready to merge"]
    S13["13. Memory flush"]

    ISSUE --> S1
    CTX --> S1
    S1 --> S2
    S2 -- "scope decisions" --> ISSUE
    S2 --> S3 --> S4 --> S5
    S5 -- "an entry when a document goes stale" --> LIST
    S5 --> S6 --> S7
    S7 -- "opens" --> PR
    PR -- "CI results, review comments" --> S8
    S7 --> S8 --> S9
    S9 -- "goal, target, constraints, prior findings" --> RT
    RT -- "verdict and scored findings" --> S9
    S9 --> S10 --> S11
    LIST -- "open entries" --> S11
    S11 -- "target, stale-docs list, owner's notes" --> HI
    HI -- "edits for the listed entries" --> DOCS
    HI -- "report: applied, not applied, found beyond the list" --> S11
    S11 --> S12 --> S13
    S13 -- "delete, condense, keep" --> NOTES
```

What each subagent receives and returns:

| Subagent | Runs at | Receives | Returns |
|---|---|---|---|
| red-team | Stage 9, on the finished change | The goal (the issue and its decided scope), the target (branch, commit range or pull request), the constraints (what is out of scope), and prior findings on a re-review | A verdict and scored findings, each with evidence. It edits nothing. |
| historian | Stage 11, once the change is final | The target, the stale-docs list, and the owner's notes on entries already rejected or changed | Edits for the listed entries, and a report: what it applied, what it did not apply and why, and what it found beyond the list. It edits nothing beyond the list and never commits. |

## Skeleton

Copy the block, replace every `<placeholder>`, and remove the stages or subagents your project does not use. Mermaid reads angle brackets as HTML, so a placeholder left in place renders as an empty label.

Placeholders: `<review subagent>`, `<documentation subagent>`, `<context documents>`, `<project documentation>`, `<what the review subagent receives>`, `<what it returns>`, `<what the documentation subagent receives>`, `<what it returns>`.

````markdown
```mermaid
flowchart TD
    ISSUE[/"Issue and its comments"/]
    CTX[/"<context documents>"/]
    LIST[/"Stale-docs list"/]
    PR[/"Pull request"/]
    DOCS[/"<project documentation>"/]

    RT(["<review subagent>"])
    HI(["<documentation subagent>"])

    S1["1. Gather all relevant information"]
    S2["2. Settle open questions and decisions"]
    S3["3. Plan the issue's sub-phases"]
    S4["4. Plan the implementation of each phase"]
    S5["5. Implement"]
    S6["6. Test and refine"]
    S7["7. Open a pull request"]
    S8["8. Monitor CI and comments"]
    S9["9. Last pass and review scan"]
    S10["10. Fix comments and findings"]
    S11["11. Documentation pass"]
    S12["12. Ready to merge"]

    ISSUE --> S1
    CTX --> S1
    S1 --> S2
    S2 -- "scope decisions" --> ISSUE
    S2 --> S3 --> S4 --> S5
    S5 -- "an entry when a document goes stale" --> LIST
    S5 --> S6 --> S7
    S7 -- "opens" --> PR
    PR -- "CI results, review comments" --> S8
    S7 --> S8 --> S9
    S9 -- "<what the review subagent receives>" --> RT
    RT -- "<what it returns>" --> S9
    S9 --> S10 --> S11
    LIST -- "open entries" --> S11
    S11 -- "<what the documentation subagent receives>" --> HI
    HI -- "<what it returns>" --> DOCS
    S11 --> S12
```
````

## Examples

Diagrams from BabyBuddyHelper and InvoiceMe arrive in `Examples/` with [#7](https://github.com/MatheusCastro99/AgenticDevelopmentWorkflow/issues/7).
