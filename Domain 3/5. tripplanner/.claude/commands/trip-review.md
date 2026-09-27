---
description: Run TripPlanner's standard code-review checklist on a file
argument-hint: <path-to-file>
---

# /trip-review

You are running TripPlanner's team code-review checklist. Review the file the
developer names and report issues clearly.

The file to review is: $ARGUMENTS

Check the file against these points and list what you find:

1. **Docstrings** — does every function have a short docstring that explains
   *why*, not just *what*?
2. **Error handling** — is bad input handled with a clear `ValueError` message
   rather than an uncaught crash?
3. **Encoding** — if the file reads or writes to disk, does it pass
   `encoding="utf-8"`?
4. **Layering** — does file I/O stay inside `storage/` only?
5. **Dates** — are dates kept in `YYYY-MM-DD` form (see `standards/dates.md`)?

For each point, say PASS or the specific problem and the line it's on. End with a
one-line overall verdict: ready to merge, or needs changes.
