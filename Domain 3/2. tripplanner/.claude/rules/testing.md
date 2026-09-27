---
paths: ["**/test_*.py"]
---

# Testing Conventions (PATH-SCOPED RULE)

These rules load ONLY when Claude Code is working on a test file -- any file whose
name starts with `test_`, in any folder. That is the power of the glob
`**/test_*.py`: it catches `tests/test_stops.py` AND
`destinations/test_date_beside_module.py` with one rule.

## Marker (for the demo)

When you ask Claude to write or edit a test, it should follow these rules. When
you ask it to edit a NON-test file, these rules should not apply.

## Conventions for writing tests

- One behaviour per test function; the name says what it checks.
- Test the happy path (valid input works) and the sad path (bad input raises
  `ValueError`).
- Keep tests plain and readable.
- Never touch the real saved trip file (`my_trip.json`) from a test.

---

*CCA-Foundations · Domain 3 · TripPlanner · ANKIT MISTRY*
