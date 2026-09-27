---
name: analyze-codebase
description: Produce a full structural analysis of the TripPlanner project - every folder, every module, and how they fit together. Use when you want a complete map of the codebase without cluttering your main chat.
context: fork
allowed-tools: ["Read", "Grep", "Glob"]
argument-hint: [optional-folder-to-focus-on]
---

# Analyze Codebase

You are producing a **complete structural analysis** of the TripPlanner project.
This is deliberately verbose - that is exactly why this skill runs in a forked
context (`context: fork`), so all this detail stays OUT of the developer's main
conversation.

If the developer named a folder in $ARGUMENTS, focus on that folder. Otherwise
analyse the whole project.

Produce:

1. **Folder map** - list every folder and one line on what it is for.
2. **Module-by-module** - for each `.py` file: its purpose, the key functions it
   defines, and what it imports from other modules.
3. **Data flow** - trace how a stop travels from raw text to saved JSON
   (parsing -> destinations -> storage).
4. **Observations** - anything notable: duplication, missing tests, tight spots.

## Why the frontmatter matters

- `context: fork` - runs this in an isolated sub-agent context. The long output
  above does NOT pollute the main chat; only a short summary comes back.
- `allowed-tools: ["Read", "Grep", "Glob"]` - this skill may only READ and SEARCH.
  It cannot Write, Edit, or run Bash. A read-only analysis skill has no business
  changing files, so we lock it down. This is a safety boundary.
- `argument-hint: [optional-folder-to-focus-on]` - reminds the developer they can
  pass a folder to narrow the analysis.

End with a SHORT summary (3-5 lines) suitable for returning to the main chat.
