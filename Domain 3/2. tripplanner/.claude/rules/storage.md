---
paths: ["storage/**/*.py"]
---

# Storage Conventions (PATH-SCOPED RULE)

These rules load ONLY when Claude Code is working inside the `storage/` folder.
The glob `storage/**/*.py` matches any Python file under `storage/`.

This shows a second kind of scoping: where `**/test_*.py` selects files by NAME
wherever they are, `storage/**/*.py` selects files by LOCATION.

## Marker (for the demo)

When you ask Claude to edit a file in `storage/`, it should follow these rules.
When you ask it to edit a file in another folder, these rules should not apply.

## Conventions for storage code

- All disk reads/writes happen here and nowhere else in the app.
- Always pass `encoding="utf-8"` to `open(...)`.
- If the trip file does not exist yet, return an empty list -- never crash.
- Write the whole trip on every save.

---

*CCA-Foundations · Domain 3 · TripPlanner · ANKIT MISTRY*
