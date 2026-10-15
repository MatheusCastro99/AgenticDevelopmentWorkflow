# UI Guidelines

## What this file is for

It holds the interface and experience guardrails: what the product should feel like, and the principles every screen, component and flow follows.

The main session reads it before any interface work, and the [ux-design](../Skills/UX_Design.md) skill applies it as its authority.

A project with a user interface needs this page. A project without one, such as a library, a command-line tool or an API with no client of its own, may leave it out.

## What goes in it, and what stays out

Goes in:

- The identity: how the product should feel, and what it must not feel like
- A few core principles, each with what to favor and what to avoid
- The visual direction for color, type and layout, given as directions and not as values
- The purpose of each screen, and the questions it answers for the user
- Interaction patterns: actions, confirmations, feedback
- Where the design system lives, and the rules for using it
- Accessibility: what to favor and what to avoid
- Anti-patterns: what the interface must never become
- The questions to ask before an interface change is approved

Stays out:

- The values of colors, sizes and styles. They live in the project's style files; this page names the files.
- How a review is run. That is in the [ux-design](../Skills/UX_Design.md) skill.
- Standing rules about screens, such as one editing page for each kind of record. They are in [Decisions and Consistency](Decisions_Consistency.md).
- Where the screen files sit. That is in the [architecture document](Architecture_Design.md).
- The product vision itself. It is in the vision document, which this page links to.

## Skeleton

Copy the page outline and replace the text in angle brackets. Repeat a `###` block for each principle and each screen.

Placeholders: `<date>`, `<project>`, `<path>`, `<principle>`, `<screen>`, `<style-files>`, and the text in angle brackets in the outline.

```markdown
# UI Guidelines

Last updated: <date>

## Purpose
The interface and experience guardrails for <project>. They keep every screen in line with the [Project Vision](<path>): <the vision in one sentence>.

## Identity
Feels:
- <warm, calm, precise, …>

Avoid:
- <what it must not feel like>

## Principles

### <principle>
<One sentence on what it means for the interface.>

Favor:
- <…>

Avoid:
- <…>

## Visual direction
- Color: <the direction, and what to avoid>
- Type: <the direction, and what to avoid>
- Layout: <the direction, and what to avoid>

## Screens

### <screen>
Purpose: <what the screen is for>

Answers:
- <a question the user brings to this screen>

## Interaction patterns
- Actions: <how primary and secondary actions look and behave>
- Confirmations: <when the interface asks first>
- Feedback: <how success and failure are shown>

## Design system
Lives in: <style-files>

Rules:
- <how styles and tokens are used, and what is never hardcoded>

## Accessibility
Favor:
- <contrast, target sizes, labels, …>

Avoid:
- <…>

## Anti-patterns
- <what the interface must never become>

## Review questions
Before approving an interface change, ask:
- <Does it feel the way the identity says it should?>
- <…>
```

## Examples

Excerpts from BabyBuddyHelper's UI guidelines arrive in `Examples/` with [#7](https://github.com/MatheusCastro99/AgenticDevelopmentWorkflow/issues/7).
