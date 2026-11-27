# Documentation repo — instructions for Claude

Customer-facing manuals for the mitchsf clocks and InfoServer. Each manual is a
`.docx` source with a matching `.pdf` beside it. Two people edit this repo, each
from their own clone, each with their own Claude Code.

## Collaboration rules

- **One person per `.docx` at a time.** Git cannot merge Word files. Before
  editing a manual, confirm the user has claimed it with the other editor.
- **Always `git pull` before the first edit of a session.** If the pull brings
  in changes to the file you are about to edit, tell the user before going on.
- **Commit and push as soon as an edit is done.** Do not leave manual changes
  uncommitted at the end of a session.
- **Rebuild the PDF from the `.docx` in the same commit**, so the two always match.
- **On a `.docx` conflict**, never try to merge. Keep the already-pushed version
  (`git checkout --theirs <file>`) unless the user says otherwise, commit, and
  tell the user which edits must be redone by hand.
- Never commit the `* BACKUP *.docx` working copies (they are gitignored).

## Content rules (customer documents)

- **Never print provisioning / model codes (the 404xxx numbers).** They
  authenticate a board as genuine. Name models by product name only.
- **Document settings and their ranges, never hardware quantities.** No
  per-model LED counts, chip types, or "configurable from N to M" hardware
  options. Setting ranges the reader operates (e.g. "Crossfade Duration 0-9")
  are fine.
- **The shared Zev-7 Operator Manual carries only its own revision number**
  (e.g. "Version 3.2 (Nov 2026)"), never a firmware version: it covers several
  products whose firmware versions differ. Do not add or "sync" one.
- Touch-disables-rules (a settings change while a rule is in effect turns the
  rules off) is documented in the manuals only, not in the firmware UI.

## Commit messages

Name the manual and its new revision, then what changed, for example:
`Zev-7 Operator Manual version 3.2 (Nov 2026): <what changed>`.
