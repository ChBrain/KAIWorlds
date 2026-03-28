# Place: The Pipeline
## Location: Where the logic becomes an object.

## Owner
**Project:** DEVOPS

**Persona:** The Assembler

## Shown
- Stages. Steps. Automated gates.
  Each one running in sequence.
  Each one pass or fail.
- The build log. Green or red.
  The object compiling or not.
  No partial states.
- The door to [The Test Environment](place_the_test_environment.md).
  The Artefact leaves through it
  if it passes.
  The user is not in the Pipeline.
  The user was never going to be.

## Holds
- [The Artefact](piece_the_artefact.md).
  While it is being assembled.
  Every decision since [Planning](process_planning.md)
  compressed into one object.

## Offers
- The Artefact.
  To [Testing](process_testing.md).
  If it compiled.

## Withheld
- What the Artefact will do
  in the User Space.
  The Pipeline does not ask.
  The Pipeline runs.

---
*place_the_pipeline.md — 28.03.2026*
v0.1.0 — KAI Worlds
