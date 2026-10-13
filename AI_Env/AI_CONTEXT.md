# AI Context

## What this file is for

It is the page an agent loads first. It says in a few lines what the project is, then points to every context document with one line on what that document holds.

The agent's guidance file (for Claude Code, `CLAUDE.md`) tells it to read this page before planning or editing anything. From here it reaches the rest.

## What goes in it, and what stays out

Goes in:

- A short summary of the project: what it is and who it is for
- A link to each context document, with one line on what it answers
- Links to the project's own documents (vision, requirements, roadmap)
- The date it was last updated

Stays out:

- Anything that has its own document. Link to it; do not repeat it, or the two copies drift apart.
- Rules about how the agent behaves in the repository. They are in the agent's guidance file.
- The state of the current issue. That lives in the issue.

## The index

This is the index of this kit. Pages that arrive with a later phase are named in plain text and become links when they exist.

### This repository

- [README](../Docs/README.md): overview and status
- [Project Vision](../Docs/Project_Vision.md): what the kit is and is not
- [PRD](../Docs/PRD.md): what the kit contains and what it must do
- [Project Roadmap](../Docs/Project_Roadmap.md): phases and their status

### Context documents

| Page | What it answers |
|---|---|
| [Development Workflow](Context/Development_Workflow.md) | Which stages does an issue go through, and what is approved at each? |
| [Working Agreements](Context/Working_Agreements.md) | Who decides, how is a recommendation made, how is a finding triaged, where is a decision recorded? |
| [Data Flow](Context/DataFlow.md) | Where does each subagent run, and what moves between the stages? |
| `Context/Architecture_Design.md` (#6) | How is the project structured, and which files matter? |
| `Context/UI_Guidelines.md` (#6) | What must the interface look and feel like? |
| `Context/Current_Focus.md` (#6) | What is being worked on now? |
| `Context/Decisions_Consistency.md` (#6) | Which standing rules must every change follow? |

### Agents and skills

| Page | What it answers |
|---|---|
| `Agents/Red_Team.md` (#4) | Why is there an independent reviewer, and how is it configured and briefed? |
| `Agents/Historian.md` (#4) | Why is there a documentation updater, and how is it configured and briefed? |
| `Skills/Guardrails_Review.md` (#5) | What does the project review checklist check? |
| `Skills/UX_Design.md` (#5) | What does the interface and copy review check? |

### Templates and examples

- [Stale-docs list](../Templates/stale-docs.md): the running list a change keeps for the documentation pass
- `Templates/agents/` and `Templates/skills/` (#4, #5): copy-ready definitions
- `Examples/` (#7): the same pieces as filled in on BabyBuddyHelper and InvoiceMe

## Skeleton

```markdown
# AI Context

Last updated: <date>

## Project
<Two or three sentences: what the project is, who it is for, what it values.>

- [Project Vision](<path>)
- [Requirements](<path>)
- [Roadmap](<path>)

## Context documents
| Page | What it answers |
|---|---|
| [Architecture Design](<path>) | How is the project structured, and which files matter? |
| [Current Focus](<path>) | What is being worked on now? |
| [Decisions](<path>) | Which standing rules must every change follow? |
| [UI Guidelines](<path>) | What must the interface look and feel like? |
| [Development Workflow](<path>) | Which stages does an issue go through? |
| [Working Agreements](<path>) | Who decides, and how? |
| [Data Flow](<path>) | Where does each subagent run? |

## Agents and skills
| Page | What it answers |
|---|---|
| [<agent or skill>](<path>) | <what it is for> |
```

## Examples

Excerpts showing an index page on a real project arrive in `Examples/` with [#7](https://github.com/MatheusCastro99/AgenticDevelopmentWorkflow/issues/7).
