# InvoiceMe examples

How [InvoiceMe](https://github.com/MatheusCastro99/InvoiceMe), a MERN app for managing customers and invoices, uses the kit's pieces. Each section links to the project's file at commit [`c51f217`](https://github.com/MatheusCastro99/InvoiceMe/tree/c51f217c19c6df22da102af884f276fafde011d8).

## Architecture Design

[`docs/architecture-overview.md`](https://github.com/MatheusCastro99/InvoiceMe/blob/c51f217c19c6df22da102af884f276fafde011d8/docs/architecture-overview.md)

One Mermaid diagram of the system, from the React frontend through the Express API to MongoDB, then each part's responsibilities and the planned extensions. The folder tree is in [`docs/README.md`](https://github.com/MatheusCastro99/InvoiceMe/blob/c51f217c19c6df22da102af884f276fafde011d8/docs/README.md), under "Project Architecture".

## Data Flow

[`docs/save-workflows.md`](https://github.com/MatheusCastro99/InvoiceMe/blob/c51f217c19c6df22da102af884f276fafde011d8/docs/save-workflows.md)

Two Mermaid diagrams that trace a save, one for a customer and one for a final invoice, from the page's save handler through the route, validation and controller to MongoDB.

## Decisions and Consistency

[`docs/Decisions.md`](https://github.com/MatheusCastro99/InvoiceMe/blob/c51f217c19c6df22da102af884f276fafde011d8/docs/Decisions.md)

The standing rules, ADR-001 to ADR-009. Two are pending until the Schema epic lands, and ADR-001 writes the request, response and failure paths as one rule.

## Red Team

[`AI_Environment/Agents/red-team.md`](https://github.com/MatheusCastro99/InvoiceMe/blob/c51f217c19c6df22da102af884f276fafde011d8/AI_Environment/Agents/red-team.md)

Adapted from BabyBuddyHelper's, with the checks rewritten for Express and Mongoose. Its output also lists docs made stale, for the historian's list.

## Historian

[`AI_Environment/Agents/historian.md`](https://github.com/MatheusCastro99/InvoiceMe/blob/c51f217c19c6df22da102af884f276fafde011d8/AI_Environment/Agents/historian.md)

Adapted from BabyBuddyHelper's. It fixes stale docs beyond the list, never writes `Decisions.md`, and returns a map from each change to the docs it updated.

## Guardrails Review

[`AI_Environment/Skills/review-guardrails.md`](https://github.com/MatheusCastro99/InvoiceMe/blob/c51f217c19c6df22da102af884f276fafde011d8/AI_Environment/Skills/review-guardrails.md)

Called `review-guardrails`. It records the skill's design: one check for each ADR, plus known regression traps, each reproduced against the running API.
