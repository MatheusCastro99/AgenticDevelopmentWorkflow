# Stale-docs list

<!--
Template. Copy this file into your project, fill the placeholders, then delete this comment.

Placeholders:
- <PR>        the pull request number, and the issue it closes
- <path>      a documentation file, with a section heading or line range
- <what's stale>, <what it should say>   see "Entry format" below
- <evidence>  the file, commit or issue that makes the new text true
- <n>         a count from the historian's report
- <date>      the day the entries were closed
- <commit>    the commit that carries the documentation changes

Where to keep it: this is the main session's working file, not project documentation.
Keep it out of version control (for example `.claude/stale-docs.md`, ignored), or keep
the same entries in the session and hand them over in chat or in the pull request body.
The entry format is the same either way.
-->

The main session's running list of project documentation that a change has made stale.

The list has two possible homes, and the entry format is the same in both:

- **An ignored file** (this one), when the work spans several sessions or you want to keep the cross-check log under Closed.
- **The session itself,** with the entries handed over in chat or in the pull request body, when the issue is finished in one sitting.

How it is used:

- Add an entry at the moment a change makes a document untrue, not at the end of the issue.
- Before the merge, the open entries for the pull request are the historian's brief.
- The historian's report is a cross-check of this list:
  - anything it reports beyond the list is something the list missed;
  - anything it does not apply is an entry that was wrong.
- An entry moves to Closed once the documentation changes are committed.

## Entry format

`ID · file and location · what's stale → what it should say · evidence`

| Part | What to write |
|---|---|
| ID | `D1`, `D2`, … numbered per pull request; `P1`, `P2`, … for entries under Already existed |
| File and location | The path, with a section heading or line range |
| What's stale | What the document says now, and why it is wrong |
| What it should say | Suggested text, or the facts to state |
| Evidence | The file, commit or issue that makes it true |

Example:

- D1 · `docs/README.md`, "Getting started" · says "Node.js 18+" → Node.js 20+ · `package.json` engines

---

## Open

### PR <PR>

- D1 · `<path>` · <what's stale> → <what it should say> · <evidence>

---

## Already existed

Stale documentation the change did not cause. Reported, not fixed in this pull request.

- P1 · `<path>` · <what's stale> → <what it should say> · <evidence>

---

## Closed

### PR <PR>: closed <date>, in <commit>

- D1 · `<path>` · <what's stale> → <what it should say> · <evidence>

Cross-check: the historian applied <n> of <n> entries, did not apply <n>, and reported <n> beyond the list.
Missed by the list: <what, and what would have caught it>
