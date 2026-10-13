# UX Design

## What this file is for

It documents the `ux-design` skill: a UX and UI lens the main session applies alongside its own context. It keeps screens, styling and user-facing copy consistent with the product's identity and its design system, and accessible.

It is a skill and not a subagent because the lens works on the context the session already holds. Rebuilding that context in a subagent would cost more than the lens returns. It runs inline, and no agent preloads it.

## What goes in it, and what stays out

Goes in the skill:

- Procedure: which documents and files to load
- The checks: identity, screen purpose, design system, accessibility, flow, copy, platform caveats
- The existing debt that is known and is not a regression
- The output format

Stays out:

- **The identity, the palette, the typography and the purpose of each screen.** A skill holds procedure, not project truth. Those live in the UI guidelines document, described in `Context/UI_Guidelines.md` (#6); the skill names that document as the authority and applies it.
- **Authority.** The skill recommends; the owner decides.
- A view of the running app. The skill reads the source of a screen. It cannot see the result, so it ends with what the owner should look at on screen.

## When to use it

- Designing or reviewing a screen or a component
- Changing styles, colors or layout
- Writing user-facing text: messages, labels, empty states
- Planning a redesign

Claude Code loads it when its description matches the task, or on demand with `/ux-design`.

## What it checks

| Check | What it asks |
|---|---|
| Identity | Does it feel the way the guidelines say the product should feel? |
| Screen purpose | Does the screen still answer the question the guidelines give it? |
| Design system | Are the existing styles and tokens used? A hardcoded color or size in new or changed interface code is a finding; the existing cases are listed as known debt. |
| Accessibility | Text contrast of at least 4.5:1 (3:1 for large text), minimum touch targets, an accessible name where the visual does not explain itself, and state never shown by color alone. It is never traded for looks. |
| Flow | One clear primary action per screen, no hidden actions, and the flow rules that come from a standing rule |
| Copy | Short and specific, in the voice the guidelines set |
| Platform caveats | What the owner's manual pass does not cover on this platform |

## Output

- The design goal: the problem being solved
- An identity-alignment rating: low, medium or high
- Findings, each with `file:line`, what is wrong and the suggested change
- An accessibility result: pass, or the specific failures
- A recommendation (approve, adjust or redesign) with its advantages and disadvantages
- What the owner should check on screen

## How the two projects differ

Only BabyBuddyHelper has this skill. InvoiceMe has none.

BabyBuddyHelper's skill names its screens and the question each one answers, and calls its rating "companion alignment", after the product's identity. The template leaves both to the UI guidelines document and calls the rating "identity alignment".

## Skeleton

The copy-ready skill is [Templates/skills/ux-design/SKILL.md](../../Templates/skills/ux-design/SKILL.md). Copy it to `.claude/skills/ux-design/SKILL.md`, fill the placeholders listed in its opening comment, and delete that comment.

| Placeholders | What they hold |
|---|---|
| `<project>` | The project's name |
| `<ui-guidelines-doc>` | The path of the document that is the authority |
| `<style-token-files>`, `<ui-source-paths>` | Where the tokens and the screens live |
| `<known-debt>`, `<new-token-rule>` | The existing hardcoded values, and where a new token is added |
| `<touch-target-minimums>` | The minimum touch target on each platform |
| `<flow-checks>` | Flow rules that come from a standing rule, with their IDs |
| `<platform-caveats>` | What the manual pass does not cover |

## Examples

Excerpts from BabyBuddyHelper's `ux-design` documentation arrive in `Examples/` with [#7](https://github.com/MatheusCastro99/AgenticDevelopmentWorkflow/issues/7).
