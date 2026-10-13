# AgenticDevelopmentWorkflow

[![Link Check](https://github.com/MatheusCastro99/AgenticDevelopmentWorkflow/actions/workflows/link-check.yml/badge.svg)](https://github.com/MatheusCastro99/AgenticDevelopmentWorkflow/actions/workflows/link-check.yml)
[![Status](https://img.shields.io/badge/Status-In%20Progress-orange)](https://github.com/MatheusCastro99/AgenticDevelopmentWorkflow/issues/1)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue)](../LICENSE)

AgenticDevelopmentWorkflow documents how I work with an AI coding agent on a real project: the context it reads, the rules it follows, the subagents and skills it uses, and the stages every issue goes through.

It is a kit. Each piece explains what it is for, gives a skeleton to fill in, and shows how it was filled in on two projects built this way: [BabyBuddyHelper](https://github.com/MatheusCastro99/BabyBuddyHelper) (.NET MAUI) and [InvoiceMe](https://github.com/MatheusCastro99/InvoiceMe) (MERN).

The repository is being built now, with the workflow it documents. See [Status](#status) for what exists today.

---

## Who it is for

Developers looking for an organized, structured way to start agentic development in their projects.

The guide applies to any platform that supports its requirements: parallel agents, context management and skills. The copy-ready definitions in `Templates/` are written for Claude Code.

## The approach in short

- **The owner decides.** The agent recommends, with trade-offs, and says so when the path looks sub-optimal.
- **Context is written down.** The agent loads the project's own documents before it plans or edits anything.
- **Decisions are standing rules.** A reviewer can check a change against them.
- **Every issue goes through the same stages,** in order, and each stage is approved before the next one starts.
- **Review is independent.** A subagent with no stake in the change tries to break it before the owner sees it.
- **Documentation is part of the change.** What a change makes stale is tracked on a running list and fixed before the merge.
- **Simple first.** Add structure when the project needs it, not before.

The full version is in [Project Vision](Project_Vision.md).

---

## What is in the kit

| Piece | Where | What it gives you |
|---|---|---|
| Context documents | `AI_Env/Context/` | What each document is for, what goes in it, and a skeleton |
| Context index | `AI_Env/AI_CONTEXT.md` | The page an agent loads first |
| Agents | `AI_Env/Agents/` | Why each subagent exists, when to use it, how it is configured |
| Skills | `AI_Env/Skills/` | What each skill checks and when to use it |
| Templates | `Templates/` | Copy-ready agent and skill definitions, and the stale-docs list |
| Examples | `Examples/` | The same pieces as filled in on BabyBuddyHelper and InvoiceMe |

## Structure

```text
AgenticDevelopmentWorkflow/
│
├── .claude/
│   └── CLAUDE.md
│
├── .github/
│   └── workflows/
│       └── link-check.yml
│
├── Docs/
│   ├── README.md
│   ├── Project_Vision.md
│   ├── Project_Roadmap.md
│   └── PRD.md
│
├── AI_Env/
│   ├── AI_CONTEXT.md
│   ├── Context/
│   │   ├── Architecture_Design.md
│   │   ├── UI_Guidelines.md
│   │   ├── Current_Focus.md
│   │   ├── Decisions_Consistency.md
│   │   ├── Development_Workflow.md
│   │   ├── DataFlow.md
│   │   └── Working_Agreements.md
│   ├── Agents/
│   │   ├── Red_Team.md
│   │   └── Historian.md
│   └── Skills/
│       ├── UX_Design.md
│       └── Guardrails_Review.md
│
├── Templates/
│   ├── agents/
│   ├── skills/
│   └── stale-docs.md
│
├── Examples/
│   ├── BabyBuddyHelper/
│   └── InvoiceMe/
│
└── LICENSE
```

`Docs/` holds this repository's own documents. `AI_Env/`, `Templates/` and `Examples/` are the kit.

Runnable agent and skill definitions in `.claude/agents` and `.claude/skills` are personal tooling and are not tracked, here or in the two source projects. `Templates/` holds the versions meant to be copied.

---

## Status

| Phase | Issue | Status |
|---|---|---|
| 1. Planning and scaffold | [#2](https://github.com/MatheusCastro99/AgenticDevelopmentWorkflow/issues/2) | Done |
| 2. Workflow core | [#3](https://github.com/MatheusCastro99/AgenticDevelopmentWorkflow/issues/3) | Done |
| 3. Agents | [#4](https://github.com/MatheusCastro99/AgenticDevelopmentWorkflow/issues/4) | Done |
| 4. Skills | [#5](https://github.com/MatheusCastro99/AgenticDevelopmentWorkflow/issues/5) | Done |
| 5. Context templates | [#6](https://github.com/MatheusCastro99/AgenticDevelopmentWorkflow/issues/6) | Planned |
| 6. Examples | [#7](https://github.com/MatheusCastro99/AgenticDevelopmentWorkflow/issues/7) | Planned |

Today the repository holds its own documents in `Docs/`, the workflow core (the context index, the `Development_Workflow`, `Working_Agreements` and `DataFlow` pages, and the stale-docs list template), and the agents and skills: the red-team and historian pages, the guardrails review and UX design pages, and a copy-ready definition for each in `Templates/`. The four remaining context pages and all of `Examples/` arrive with phases 5 and 6.

Details are in the [Project Roadmap](Project_Roadmap.md).

## Documentation

| File | Purpose |
|---|---|
| [Project_Vision.md](Project_Vision.md) | What the kit is, what the approach is, and what it is not |
| [PRD.md](PRD.md) | What the kit contains and what it must do |
| [Project_Roadmap.md](Project_Roadmap.md) | Phases and their status |

---

## License

[MIT](../LICENSE)

## Author

**Matheus Castro**

Repository:
https://github.com/MatheusCastro99/AgenticDevelopmentWorkflow
