---
name: ux-design
description: UX and UI lens for <project>. Checks screens, interface changes, flows and copy against the product identity, the UI guidelines, the shared style tokens and basic accessibility. Use when designing or reviewing a screen or component, touching styling, writing user-facing text (messages, labels, empty states), or planning a redesign.
---

<!--
Template. Copy this file to `.claude/skills/ux-design/SKILL.md` in your project,
fill the placeholders, then delete this comment. The frontmatter must stay on line 1.

Placeholders:
- <project>                 the project's name
- <ui-guidelines-doc>       path to the document that holds the identity, principles,
                            palette, typography and the purpose of each screen
- <style-token-files>       the files that hold the colors, sizes and named styles, with one
                            line on how the interface reads them
- <ui-source-paths>         where the screens and components live
- <known-debt>              existing hardcoded values that are not a regression, by file
- <new-token-rule>          where a new color, size or style is added
- <touch-target-minimums>   the minimum touch target on each platform the project ships to
- <flow-checks>             flow rules that come from a standing rule, each with its rule ID
- <platform-caveats>        what the owner's manual pass does not cover on this platform
                            (unusual window sizes, a second theme, …)
-->

# UX Design

This skill adds a UX lens on top of the session context. It produces a **recommendation**. The project owner decides.

## 1. Load context

- `<ui-guidelines-doc>` is **the authority**: identity, principles, palette, typography, screen purposes. Don't restate it; apply it.
- <style-token-files>
- The source of the screen or component being changed, in `<ui-source-paths>`.

You can't see the running app. Base findings on the source and say what the owner should look at on screen.

## 2. Check

**Identity.** Does it feel the way the guidelines say the product should feel? Name the guideline a finding goes against.

**Screen purpose.** Does the screen still answer the question the guidelines give it?

**Design system.**
- Use the existing styles and tokens. A hardcoded color or size in **new or changed** interface code is a finding.
- Known existing debt; don't report it as a regression: <known-debt>.
- <new-token-rule>
- Prefer reusing an existing layout pattern over a one-off.

**Accessibility.** This is never traded for looks.
- Text contrast is at least 4.5:1 (3:1 for large text).
- Touch targets are at least <touch-target-minimums>.
- Interactive elements carry an accessible name or description where the visual isn't self-explanatory.
- State is never shown by color alone.

**Flow.** One clear primary action per screen, and no hidden actions or deep navigation. <flow-checks>

**Copy.** Short and specific, in the voice the guidelines set.

**Platform caveats.** <platform-caveats>

## 3. Output

- **Design goal:** the problem being solved
- **Identity alignment:** Low / Medium / High
- **Findings,** each with `file:line`, what's wrong, and the suggested change to the interface code or the copy
- **Accessibility result:** pass, or the specific failures
- **Recommendation:** Approve / Adjust / Redesign, with advantages and disadvantages
- **Check on screen:** the specific things the owner should look at while running the app
