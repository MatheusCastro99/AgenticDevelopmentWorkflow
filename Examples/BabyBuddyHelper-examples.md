# BabyBuddyHelper examples

How [BabyBuddyHelper](https://github.com/MatheusCastro99/BabyBuddyHelper), a .NET MAUI parenting companion, uses the kit's pieces. Each section links to the project's file at commit [`2c6974a`](https://github.com/MatheusCastro99/BabyBuddyHelper/tree/2c6974a43212ec72071d4d653c5a510ca6cc2662).

## AI Context

[`docs/ai/AI_CONTEXT.md`](https://github.com/MatheusCastro99/BabyBuddyHelper/blob/2c6974a43212ec72071d4d653c5a510ca6cc2662/docs/ai/AI_CONTEXT.md)

Opens with the index: a summary of the vision and a link to each context document. Below the index, the same file keeps the core entities, the data source and persistence, the editing workflow and the known technical debt.

## Architecture Design

[`docs/ai/context/ARCHITECTURE_DESIGN.md`](https://github.com/MatheusCastro99/BabyBuddyHelper/blob/2c6974a43212ec72071d4d653c5a510ca6cc2662/docs/ai/context/ARCHITECTURE_DESIGN.md)

The `Core/`, `UI/` and test folders with their key files, a link to the data-flow diagram, and the planned direction in its own section, citing its ADRs.

## Data Flow

[`docs/DataFlow.excalidraw`](https://github.com/MatheusCastro99/BabyBuddyHelper/blob/2c6974a43212ec72071d4d653c5a510ca6cc2662/docs/DataFlow.excalidraw)

One Excalidraw diagram of a save, from the button to `babybuddy.db3`, with its validation and database error routes. GitHub shows the file as JSON; it opens in Excalidraw.

## Current Focus

[`docs/ai/context/CURRENT_STATE.md`](https://github.com/MatheusCastro99/BabyBuddyHelper/blob/2c6974a43212ec72071d4d653c5a510ca6cc2662/docs/ai/context/CURRENT_STATE.md)

Called the current state. The status, the current epic's sub-issues in order with their state, the next issue, work outside the epic, and the open issues of the next phase.

## Decisions and Consistency

[`docs/ai/context/DECISIONS.md`](https://github.com/MatheusCastro99/BabyBuddyHelper/blob/2c6974a43212ec72071d4d653c5a510ca6cc2662/docs/ai/context/DECISIONS.md)

The standing rules, ADR-001 to ADR-018, each with a status and most with their reason.

## UI Guidelines

[`docs/ai/context/UI_GUIDELINES.md`](https://github.com/MatheusCastro99/BabyBuddyHelper/blob/2c6974a43212ec72071d4d653c5a510ca6cc2662/docs/ai/context/UI_GUIDELINES.md)

The Parenting Companion identity, four core principles, the visual direction, each screen's purpose and questions, interaction patterns, accessibility, anti-patterns and review questions.

## Red Team

[`docs/ai/agents/RED_TEAM.md`](https://github.com/MatheusCastro99/BabyBuddyHelper/blob/2c6974a43212ec72071d4d653c5a510ca6cc2662/docs/ai/agents/RED_TEAM.md)

Why it exists, when to spawn it, its configuration (read-only tools, opus at high effort, `review-guardrails` preloaded), what to brief it with and its scored output.

## Historian

[`docs/ai/agents/HISTORIAN.md`](https://github.com/MatheusCastro99/BabyBuddyHelper/blob/2c6974a43212ec72071d4d653c5a510ca6cc2662/docs/ai/agents/HISTORIAN.md)

Applies the stale-docs list before a merge. Its history records the rules added after its first runs: check every fact in an edited section, report each adaptation, compare listed sets against `git ls-files`.

## Guardrails Review

[`docs/ai/skills/REVIEW_GUARDRAILS.md`](https://github.com/MatheusCastro99/BabyBuddyHelper/blob/2c6974a43212ec72071d4d653c5a510ca6cc2662/docs/ai/skills/REVIEW_GUARDRAILS.md)

Called `review-guardrails`. A table of checks, each tied to the rule it enforces, the project's known regression traps, a severity scale, and the build and test commands.

## UX Design

[`docs/ai/skills/UX_DESIGN.md`](https://github.com/MatheusCastro99/BabyBuddyHelper/blob/2c6974a43212ec72071d4d653c5a510ca6cc2662/docs/ai/skills/UX_DESIGN.md)

Reviews screens, XAML styles and copy against the UI guidelines: identity, screen purpose, design-system tokens, accessibility, flow and copy.
